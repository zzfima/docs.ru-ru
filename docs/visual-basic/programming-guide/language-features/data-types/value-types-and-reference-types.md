---
title: "Типы значений и ссылочные типы | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], ссылочные типы"
  - "типы данных [Visual Basic], типы значений"
  - "ссылочные типы данных"
  - "ссылочные типы"
  - "типы [Visual Basic]"
  - "типы данных значений"
  - "типы значений"
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы значений и ссылочные типы
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В Visual Basic, типы данных реализованы на основе их классификации.  Типы данных [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] могут классифицироваться в соответствии с тем, хранят ли переменные таких типов собственные данные или указатель на них.  Если переменная хранит собственные данные, она имеет *тип значения*. Если переменная содержит указатель на данные в другом месте в памяти, она имеет *ссылочный тип*.  
  
## Типы значений  
 Тип данных является *типом значений*, если он содержит данные в пределах своей собственной области памяти.  К типам значения относятся:  
  
-   Все числовые типы данных  
  
-   `Boolean`, `Char` и `Date`  
  
-   Все структуры, даже если их члены являются ссылочными типами  
  
-   Перечисления, поскольку их базовый тип всегда является `SByte`, `Short`, `Integer` `Long`, `Byte`, `UShort`, `UInteger` или `ULong`  
  
 Каждая структура является типом значения, даже если она содержит члены ссылочного типа.  По этой причине типы значений как `Char` и  `Integer` реализуйте структурами платформы .NET Framework.  
  
 Можно объявить тип значения с помощью зарезервированного ключевого слова, например, `Decimal`.  Ключевое слово `New` также может быть использовано для инициализации типа значений.  Это особенно полезно, если тип имеет конструктор, принимающий параметры.  Примером этого является конструктор <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, который строит новое значение `Decimal` от предоставленных частей.  
  
## Ссылочные типы  
 *Ссылочный тип* содержит указатель на другую область памяти, содержащую данные.  К ссылочным типам относятся:  
  
-   `String`  
  
-   Все массивы, даже если их члены являются типами значений  
  
-   Типы классов, например <xref:System.Windows.Forms.Form>  
  
-   Делегаты  
  
 Класс является *ссылочным типом*.  По этой причине ссылочные типы, например `Object` и `String`, поддерживаются классами [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Обратите внимание, что любой массив является ссылочным типом, даже если он содержит элементы типа значения.  
  
 Поскольку каждый ссылочный тип, представляющий базовый класс платформы .NET Framework, необходимо использовать [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово при инициализации.  Следующий оператор инициализирует массив:  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## Элементы, которые не являются типами  
 Следующие элементы программирования не квалифицируются как типы, так как нельзя указывать ни один из них в качестве типа данных для объявленного элемента:  
  
-   Пространства имен  
  
-   Модули  
  
-   События  
  
-   Свойства и процедуры  
  
-   Переменные, константы и поля  
  
## Работа с типом данных объекта  
 Переменной типа данных `Object` можно присвоить либо тип значения, либо ссылочный тип.  Переменная `Object` всегда содержит указатель на данные, но никогда не содержит самих данных.  Однако, если присвоить тип значений переменной `Object`, то она ведет себя так, как если бы она содержала свои собственные данные.  Дополнительные сведения см. в разделе [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Можно выяснить, является ли `Object` переменная действует как ссылочный тип или тип значения, передавая его на  <xref:Microsoft.VisualBasic.Information.IsReference%2A> метод  <xref:Microsoft.VisualBasic.Information> класс   <xref:Microsoft.VisualBasic?displayProperty=fullName> пространство имен.  Метод <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=fullName> возвращает `True`, если содержимое переменной `Object` представляет ссылочный тип.  
  
## См. также  
 [Типы значения, допускающие Null](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Оператор Structure](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)