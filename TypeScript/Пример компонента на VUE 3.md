### Пример на JavaScript

В этом примере мы создадим простой компонент, который отображает имя пользователя и кнопку для изменения этого имени.

```JS
<template>
  <div>
    <p>User Name: {{ userName }}</p>
    <button @click="changeName">Change Name</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const userName = ref('Alice');

    const changeName = () => {
      userName.value = 'Bob';
    };

    return {
      userName,
      changeName
    };
  }
};
</script>
```

### Описание:

- Мы использовали Vue Composition API (в частности, `ref` для создания реактивной переменной).
- Компонент отображает имя пользователя и предоставляет кнопку для изменения этого имени.
- Вся логика написана на JavaScript, и Vue не использует типизацию.

---

### Пример на TypeScript

Теперь давай перепишем этот пример на TypeScript. Мы будем использовать строгую типизацию для переменных и функций.

```TS
<template>
  <div>
    <p>User Name: {{ userName }}</p>
    <button @click="changeName">Change Name</button>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue';

export default {
  setup() {
    const userName = ref<string>('Alice'); // Явно указываем, что userName — это строка

    const changeName = (): void => {
      userName.value = 'Bob'; // TypeScript знает, что userName — строка
    };

    return {
      userName,
      changeName
    };
  }
};
</script>
```

### Описание:

1. **`<script lang="ts">`** — эта строка указывает, что мы используем TypeScript в нашем компоненте.
2. **Типизация**:
    - Мы указали тип переменной `userName` как `ref<string>`, что позволяет явно указать, что это реактивная строка.
    - Функция `changeName` имеет явный тип возвращаемого значения `void`, так как она ничего не возвращает.
3. **Преимущества**:
    - В TypeScript ошибки с типами будут обнаружены на этапе компиляции.
    - Инструменты автодополнения лучше работают с TypeScript, что делает разработку более комфортной.

Этот пример демонстрирует базовый компонент Vue 3 как на JavaScript, так и на TypeScript. Основное отличие — это статическая типизация в TypeScript, которая помогает предотвратить ошибки и улучшить читаемость кода.