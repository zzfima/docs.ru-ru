---
title: "Тип данных, определенный пользователем | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "UserDefined"
  - "UDT"
  - "vb.UDT"
  - "User-Defined"
  - "vb.UserDefined"
  - "vb.User-Defined"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], назначение"
  - "типы данных [Visual Basic], определяемые пользователем"
  - "Structure - оператор"
  - "структуры, как пользовательские типы данных"
  - "типы [Visual Basic], определяемые пользователем"
  - "пользовательские типы данных"
  - "пользовательские типы данных, объявление структуры"
  - "пользовательские типы данных, структуры в Visual Basic"
  - "пользовательские типы данных, Visual Basic"
  - "типы, определяемые пользователем"
  - "типы, определяемые пользователем, объявление структуры"
  - "типы, определяемые пользователем, структуры в Visual Basic"
  - "типы, определяемые пользователем, Visual Basic"
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Тип данных, определенный пользователем
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит данные в определенном пользователем формате.  Оператор `Structure` определяет формат.  
  
 Предыдущие версии Visual Basic поддерживают определяемый пользователем тип данных \(UDT\).  Текущая версия расширяет UDT до *структуры*.  Структура — это объединение одного или нескольких *членов* любых типов данных.  Visual Basic обрабатывает структуру как единое целое, хотя можно получить доступ к членам по отдельности.  
  
## Заметки  
 Определяйте и используйте структуры данных, когда требуется объединить в единое целое различные типы данных, или когда ни один из простейших типов данных не подходит для выполнения требуемых условий.  
  
 Значение по умолчанию для структуры данных состоит из комбинации значений по умолчанию каждого из ее членов.  
  
## Формат объявления  
 Объявление структуры начинается с оператора [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md) и завершается оператором `End` `Structure`.  Оператор `Structure` содержит имя структуры, которая является также идентификатором типа данных, определяемых структурой.  Другие части кода могут использовать этот идентификатор для объявления переменных, параметров и возвращаемых значений функций в качестве типа данных структуры.  
  
 Объявления между операторами `Structure` и `End` `Structure` определяют члены структуры.  
  
## Уровни доступа к членам  
 Каждый член необходимо объявить с помощью оператора [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) или оператора, определяющего уровень доступа, например, [Public](../../../visual-basic/language-reference/modifiers/public.md) или [Friend](../../../visual-basic/language-reference/modifiers/friend.md) или [Private](../../../visual-basic/language-reference/modifiers/private.md).  Если используется оператор `Dim`, то уровень доступа по умолчанию является открытым \(Public\).  
  
## Советы по программированию  
  
-   **Потребление ресурсов памяти**. Как и для всех составных типов данных, нельзя точно подсчитать общее потребление ресурсов памяти структуры простым сложением номинальных объемов памяти, занимаемых отдельными членами структуры.  Более того, нельзя однозначно полагать, что порядок расположения элементов в памяти такой же, как и порядок их объявления.  Если требуется контролировать расположение структуры в памяти, можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> в операторе `Structure`.  
  
-   **Вопросы взаимодействия**. При взаимодействии с компонентами, написанными не для платформы .NET Framework, например, с объектами автоматизации или COM\-объектами, имейте в виду, что определяемые пользователем типы в других средах несовместимы с типами структуры Visual Basic.  
  
-   **Расширение**. Автоматического прямого или обратного преобразования в любой тип данных структуры не существует.  Операторы преобразования можно определить для структуры с помощью оператора [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md); кроме того, можно объявлять каждый оператор преобразования как `Widening` или `Narrowing`.  
  
-   **Символы типов**. Типы данных структуры не имеют буквенного символа или идентификатора.  
  
-   **Тип Framework.**. В платформе .NET Framework отсутствует соответствующий тип.  Все структуры наследуются от класса .NET Framework <xref:System.ValueType?displayProperty=fullName>, но ни одна из отдельных структур не соответствует классу <xref:System.ValueType?displayProperty=fullName>.  
  
## Пример  
 В следующем примере демонстрируется объявление структуры.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## См. также  
 <xref:System.ValueType>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)