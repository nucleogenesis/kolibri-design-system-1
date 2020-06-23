<template>

  <div class="screen-owner" style="position: fixed; top: 0; overflow-y:scroll; left: 0; right: 0; bottom: 0; height: 100vh; width: 100vw; background: white; padding: 12.5%; z-index: 9999;">
    <h1> Icons </h1>
    <KGrid>
      <KGridItem 
        v-for="aliases in blackIcons" 
        :key="aliases[0]"
        :layout4="{ span: 2 }"
        :layout8="{ span: 4 }"
        :layout12="{ span: 4 }"
      >
        <div>
          <KIcon :icon="aliases[0]" />
          <span style="margin-left: 8px">{{ aliases.join(", ") }}</span>
        </div>
      </KGridItem>
    </KGrid>

    <h1> Icons with Color Tokens </h1>
    <KGrid>
      <KGridItem 
        v-for="aliases in coloredIcons" 
        :key="aliases[0]"
        :layout4="{ span: 2 }"
        :layout8="{ span: 4 }"
        :layout12="{ span: 4 }"
      >
        <div>
          <KIcon :icon="aliases[0]" />
          <span style="margin-left: 8px">{{ aliases.join(", ") }}</span>
        </div>
      </KGridItem>
    </KGrid>
  </div>

</template>


<script>

  import { themeTokens } from '../styles/theme';
  import { sortedBlackIcons, sortedColoredIcons } from './iconDefinitions';

  export default {
    name: 'KIconDebug',
    computed: {
      blackIcons() {
        return sortedBlackIcons;
      },
      coloredIcons() {
        return sortedColoredIcons;
      },
    },
  };

</script>


<style scoped lang="scss">

</style>
