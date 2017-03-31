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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ecdf3c610bb09d1ecdf01e25b75c8f01802e852
ms.lasthandoff: 03/13/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a>Операторы с условием NULL (C# и Visual Basic)
Используется для проверки на значения NULL перед выполнением операции доступа к элементу (`?.`) или операции индексирования (`?[`)  Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
```vb  
Dim length = customers?.Length  ‘’ null if customers is null  
Dim first as Customer = customers?(0);  ‘’ null if customers is null  
Dim count as Integer? = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
  
```  
  
 Последний пример показывает, что операторы с условием NULL выполняют сокращенную обработку.  Если одна операция в цепочке условных операций доступа к элементу и операций индексирования возвращает значение NULL, то выполнение остальной части цепочки останавливается.  Другие операции с более низким приоритетом в выражении продолжают выполняться.  Например, `E` ниже выполняется всегда, а операции `??` и `==` выполняются.  
  
```vb-c#  
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
  
```  
  
 Другим примером использования для доступа к элементам с условием NULL является вызов делегатов в потокобезопасном режиме с существенно меньшим объемом кода.  Для старого способа требуется примерно следующий код:  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…)  
  
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
  
```  
  
 Новый способ гораздо проще:  
  
```vb-c#  
PropertyChanged?.Invoke(e)  
  
```  
  
 Новый способ является потокобезопасным, так как компилятор создает код для вычисления `PropertyChanged` только один раз, запоминая результат во временной переменной.  
  
 Необходимо явно вызывать метод `Invoke`, так как отсутствует синтаксис `PropertyChanged?(e)` для вызова делегатов с условием NULL.  Он приводил к слишком большому количеству неоднозначных ситуаций синтаксического анализа, поэтому он не разрешен.  
  
## <a name="language-specifications"></a>Спецификации языков  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор ?? (оператор объединения со значением NULL)](null-conditional-operator.md)   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)
