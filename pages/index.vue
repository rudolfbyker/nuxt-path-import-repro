<template>
  <div>{{ foo }}</div>
</template>

<script setup lang="ts">
import {stringify} from "qs";
const foo = stringify({a:1,b:2})
</script>
