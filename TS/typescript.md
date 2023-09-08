TS накладывает ограничение: 
  - на массивы. Внутри могут храниться данные только одного типа:  
  
```typescript
let items = [1, 2, 3];
items.push(4); // Все хорошо

// Argument of type 'string' is not assignable to parameter of type 'number'.
items.push('code-basics'); // Error!
```
  
  - нельзя у объекта добавлять новые свойства динамически:  
  
```typescript  
let user = {
  firstName: 'Miro',
};

// Property 'lastName' does not exist on type '{ firstName: string; }'.
user.lastName = 'Smith';
```
