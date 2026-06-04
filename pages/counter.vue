<template>

  <CounterButton
    title="Current Count"
    :count="count"
    button-text="Add +"
    @change-count="handleAdd"
  />

  <CounterButton
    title="Decrease Count"
    :count="decrease"
    button-text="Less -"
    @change-count="handleLoss"
  />




</template>


<script setup>
  const count = ref(0)
  const decrease = ref(100)

  const handleAdd = () => {
    console.log("Add button is clicked")
    count.value++
  }

  const handleLoss = () => {
    console.log("Decrease button is clicked")
    decrease.value--
  }
</script>



<!-- <template>
  <div>
    <div>
      Current count: {{ count }}
    </div>
    <div>
      <button @click="handleAdd">Add +</button>
    </div>

    <div>
      <div style="padding-top: 40px;">
        Decrease count: {{ decrease }}
      </div>
      <div>
        <button @click="handleLoss">Less -</button>
      </div>
    </div>
  </div>

</template>

<script setup>
  const count = ref(0);
  const decrease = ref(100);

  const handleAdd = () => {
    count.value = count.value + 1
  }

  const handleLoss = () => {
    decrease.value = decrease.value - 1
  }
</script> -->