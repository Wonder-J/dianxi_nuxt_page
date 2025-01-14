<template>
  <div class="layout">
    <LayoutHeader></LayoutHeader>
    <slot></slot>
    <LayoutBottom></LayoutBottom>
  </div>
</template>

<style>
.layout {
  width: 100%;
  height: 100%;
  font-family: "OPPOSans";
  color: #515a6e;
}
</style>
