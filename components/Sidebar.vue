<template>
  <div>
    <b-button v-b-toggle.sidebar-1 class="bg-transparent">
      <i class="fa fa-bars"></i>
    </b-button>
    <b-sidebar id="sidebar-1" bg-variant="info" title="Options" shadow backdrop backdrop-variant="info">
      <template #footer="{ hide }">
        <div class="d-flex bg-dark text-light align-items-center px-3 py-2">
          <strong class="mr-auto">Footer</strong>
          <b-button size="sm" @click="hide">Close</b-button>
        </div>
      </template>
      <div class="px-3 py-2">
        <ul style="line-spacing:10px;line-height:40px">
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
            <li>1</li>
        </ul>
      </div>
    </b-sidebar>
  </div>
</template>