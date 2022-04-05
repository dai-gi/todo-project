<template>
  <div id="root">
    <div class="section_title">
      <h1>Todoリスト</h1>
    </div>
    <form action="#" method="POST" id="form">
      <input type="text" name="todo_list">
    </form>
  </div>
</template>

<script>
  window.onload = function addElement() {
    const forms = document.forms;
    const forms_value = forms[0].todo_list.value;
    const element = document.createElement("p");
    element.innerText = forms_value;
    const parentElement = document.getElementsById("div")[0];
    parentElement.appendChild(element);
  }
</script>
