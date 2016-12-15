---
title: "Операторы с условием NULL (C# и Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Операторы с условием NULL (C# и Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используется для проверки на значения NULL перед выполнением операции доступа к элементу \(`?.`\) или операции индексирования \(`?[`\)  Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  
  
```c#  
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
  
```c#  
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
  
## Спецификации языка  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
 Дополнительные сведения см. в разделе [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Справочник по языку Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Руководство по программированию на Visual Basic](../../../visual-basic/programming-guide/index.md)