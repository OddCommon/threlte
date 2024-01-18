<script lang="ts">
  import { T, useFrame } from '@threlte/core'
  import { FrontSide } from 'three'
  import {
    MeshTransmissionMaterial as MeshTransmissionMaterialImpl,
    MeshDiscardMaterial
  } from '@pmndrs/vanilla'
  import { useFBO } from '../../hooks/useFBO'

  export let buffer = undefined
  export let transmissionSampler = false
  export let backside = false
  export let side = FrontSide
  export let transmission = 1
  export let thickness = 0
  export let backsideThickness = 0
  export let samples = 10
  export let resolution = undefined
  export let backsideResolution = undefined
  export let background = undefined
  export let anisotropy = undefined
  export let anisotropicBlur = undefined

  const fboBack = useFBO(backsideResolution || resolution)
  const fboMain = useFBO(resolution)

  let oldBg
  let oldTone

  useFrame((state) => {})
</script>

<T is={MeshTransmissionMaterialImpl} />
