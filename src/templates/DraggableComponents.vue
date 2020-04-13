<template>
  <div role="tablist">
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block href="#" v-b-toggle.accordion-1 variant="info">Accordion 1</b-button>
      </b-card-header>
      <b-collapse id="accordion-1" visible accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text>I start opened because <code>visible</code> is <code>true</code></b-card-text>
          
          <b-card-text><img src="https://via.placeholder.com/50" id="1" draggable="true" v-on:dragstart="dragStart"></b-card-text>
          <b-card-text><img src="https://via.placeholder.com/50" id="2" draggable="true"></b-card-text>
          <b-card-text><img src="https://via.placeholder.com/50" id="3" draggable="true"></b-card-text>
        </b-card-body>
      </b-collapse>
    </b-card>

    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block href="#" v-b-toggle.accordion-2 variant="info">Accordion 2</b-button>
      </b-card-header>
      <b-collapse id="accordion-2" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text>Option 1</b-card-text>
          <b-card-text>Option 2</b-card-text>
          <b-card-text>Option 3</b-card-text>
        </b-card-body>
      </b-collapse>
    </b-card>

    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <b-button block href="#" v-b-toggle.accordion-3 variant="info">Accordion 3</b-button>
      </b-card-header>
      <b-collapse id="accordion-3" accordion="my-accordion" role="tabpanel">
        <b-card-body>
          <b-card-text>Option 1</b-card-text>
          <b-card-text>Option 2</b-card-text>
          <b-card-text>Option 3</b-card-text>
        </b-card-body>
      </b-collapse>
    </b-card>
  </div>
</template>


<script>
export default {
  data: function() {
    return {
    };
  },
  methods: {
    dragStart: function(event) {
      console.log(event);
      event.dataTransfer.setData("Text", event.target.id);
    },
    dragging: function(event) {
      document.getElementById("demo").innerHTML =
        "The p element is being dragged";
    }
  },
  mounted() {}
};
</script>