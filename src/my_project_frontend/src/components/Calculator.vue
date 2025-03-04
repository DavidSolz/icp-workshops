<script setup>
import { ref, onMounted } from "vue";
import { my_project_backend } from "declarations/my_project_backend/index";

let a = ref(null);
let b = ref(null);
let operator = ref("+");
let result = ref("");

async function handleCalculate(e) {
  e.preventDefault();
  if (a.value === null || b.value === null) {
    result.value = "Please enter both numbers.";
    return;
  }

  try {
    const response = await my_project_backend.calculate(a.value, b.value, operator.value);
    result.value = response;
    localStorage.setItem("lastResult", response);
  } catch (error) {
    result.value = "Error occurred: " + error.message;
  }
}

onMounted(() => {
  const storedResult = localStorage.getItem("lastResult");
  if (storedResult) {
    result.value = storedResult;
  }
});
</script>
