---
title: "Операторы с условием NULL (C# и Visual Basic) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 61a093677354ba3a960fb5714963a1205d24ed06
ms.openlocfilehash: 876b7c99ca9249e0a2b9cbd036c38e368228ac9f
ms.contentlocale: ru-ru
ms.lasthandoff: 03/25/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a>Операторы с условием NULL (C# и Visual Basic)
Используется для проверки на значения NULL перед выполнением операции доступа к элементу (`?.`) или операции индексирования (`?[`)  Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 Последний пример показывает, что операторы с условием NULL выполняют сокращенную обработку.  Если одна операция в цепочке условных операций доступа к элементу и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки останавливается.  Другие операции с более низким приоритетом в выражении продолжают выполняться.  Например, `E` ниже выполняется всегда, а операции `??` и `==` выполняются.  
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.  Для старого способа требуется примерно следующий код:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 Новый способ гораздо проще:  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.  
  
 Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.  Он приводил к слишком большому количеству неоднозначных ситуаций синтаксического анализа, поэтому он не разрешен.  
  
## <a name="language-specifications"></a>Спецификации языков  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор ?? (оператор объединения со значением NULL)](null-conditional-operator.md)   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)

