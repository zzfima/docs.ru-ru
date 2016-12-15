---
title: "Тип данных Object | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Object"
  - "vb.Variant"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "типы данных [Visual Basic], назначение"
  - "Object - тип данных"
  - "Object - тип данных, справочник"
  - "объектные переменные, Тип объекта"
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип данных Object
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Содержит адреса, ссылающиеся на объекты.  Переменной `Object` можно назначить любой ссылочный тип \(строка, массив, класс или интерфейс\).  Переменная `Object` может также ссылаться на данные любого типа значения \(числовые, `Boolean`, `Char`, `Date`, структуры или перечисления\).  
  
## Заметки  
 Тип данных `Object` может указывать на данные любого типа данных, включая любой экземпляр объекта, который распознает приложение.  Используйте `Object`, когда во время компиляции не известно, на какой тип данных указывает переменная .  
  
 Значением `Object` по умолчанию является `Nothing` \(пустая ссылка\).  
  
## Типы данных  
 Переменной `Object`можно назначить переменную, константу или выражение любого типа данных.  Чтобы определить тип данных, на который в данных момент ссылается переменная `Object`, можно использовать метод <xref:System.Type.GetTypeCode%2A> класса <xref:System.Type?displayProperty=fullName>.  Это показано в приведенном ниже примере.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Тип данных `Object` является ссылочным типом.  Однако Visual Basic обрабатывает переменную `Object` в качестве типа значения, если она ссылается на данные типа значения.  
  
## Хранение  
 Независимо от того, на какой тип данных она ссылается переменная `Object`, она содержит не значения данных, а — указатель на значение.  Она всегда занимает четыре байта памяти, но не включает в себя область памяти для данных, представляющих значение переменной.  Поскольку код использует указатель для определения местоположения данных и переменных типа `Object`, доступ к ним несколько медленнее, чем к данным явно вводимых переменных.  
  
## Советы по программированию  
  
-   **Вопросы взаимодействия**. При взаимодействии с компонентами, написанными не для платформы .NET Framework, например автоматизации или COM\-объектов, следует учитывать, что типы указателей в других средах несовместимы с типом `Object` Visual Basic.  
  
-   **Производительность**. Переменная, объявленная с помощью типа `Object`, является достаточно гибкой для того, чтобы содержать ссылку на любой объект.  Однако при вызове метода или свойства для такой переменной всегда вызывается *позднее связывание* \(во время выполнения\).  Чтобы принудительно использовать *раннее связывание* \(во время компиляции\) и повысить производительность, объявите переменную с помощью имени определенного класса или преобразуйте ее к определенному типу данных.  
  
     При объявлении объектной переменной, пытайтесь использовать определенный тип класса, например <xref:System.OperatingSystem>, вместо универсального типа `Object`.  Следует также использовать определенные доступные классы, например <xref:System.Windows.Forms.TextBox>, вместо <xref:System.Windows.Forms.Control>, чтобы получить доступ к их свойствам и методам.  Обычно для нахождения возможных имен классов используется список **Classes** в **обозревателе объектов**.  
  
-   **Расширение**. Все типы данных и все ссылочные типы расширяются до типа данных `Object`.  Это означает, что можно преобразовать любой тип к типу `Object` без ошибки <xref:System.OverflowException?displayProperty=fullName>.  
  
     Однако при преобразовании типов значений и типов `Object` Visual Basic выполняет операции *boxing* и *unboxing*, которые снижают скорость выполнения.  
  
-   **Символы типа.** Тип `Object` не имеет литералов и идентификаторов.  
  
-   **Тип Framework.**. В .NET Framework соответствующим типом является класс <xref:System.Object?displayProperty=fullName>.  
  
## Пример  
 В следующем примере показано, как переменная `Object` указывает на экземпляр объекта.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## См. также  
 <xref:System.Object>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Практическое руководство. Определение наличия связи между двумя объектами](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Практическое руководство. Определение идентичности двух объектов](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)