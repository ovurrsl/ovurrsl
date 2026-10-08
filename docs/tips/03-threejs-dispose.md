# Dispose Geometries

Three.js doesn't free GPU memory on its own. Call `dispose()` when an object is removed.

```ts
useEffect(() => {
  const geometry = new THREE.BoxGeometry(1, 1, 1)
  const material = new THREE.MeshStandardMaterial({ color: 'orange' })
  const mesh = new THREE.Mesh(geometry, material)
  scene.add(mesh)

  return () => {
    scene.remove(mesh)
    geometry.dispose()
    material.dispose()
  }
}, [scene])
```

**Why:** without it, GPU buffers and textures pile up on every mount. You can watch `renderer.info.memory` grow until the tab slows down.
