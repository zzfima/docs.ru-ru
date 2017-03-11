---
title: "Эффективное использование типов данных (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AscW - функция, предпочтение Asc"
  - "ChrW - функция, предпочтение Chr"
  - "типы данных [Visual Basic], оптимизация"
  - "типы данных [Visual Basic], строгая типизация"
  - "типы данных [Visual Basic], эффективное использование"
  - "типы данных [Visual Basic], слабая типизация"
  - "оптимизация, типы данных"
  - "производительность, эффективный тип данных"
  - "строгая типизация"
  - "типизация, строгая"
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Эффективное использование типов данных (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Необъявленные переменные и переменные с необъявленными типами данных получают тип данных `Object`.  Это ускоряет написание программ, но может замедлять их выполнение.  
  
## Строгая типизация  
 Задание типов данных для всех переменных называется *строгой типизацией*.  Использование строгой типизации имеет несколько преимуществ:  
  
-   Он включает поддержку IntelliSense для переменных.  При этом можно видеть вводимые в код свойства и другие члены этих переменных.  
  
-   Используются преимущества проверки типа во время компиляции.  Благодаря этому обнаруживаются операторы, которые могут вызвать сбой во время выполнения, например из\-за ошибки переполнения.  Также обнаруживаются вызовы методов для объекта, который их не поддерживает.  
  
-   Обеспечивается более быстрое выполнение кода.  
  
## Наиболее эффективные типы данных  
 Для переменных, которые никогда не содержат дробных значений, более эффективно использовать целые типы данных вместо нецелых.  В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] наиболее эффективными типами данных являются `Integer` и `UInteger`.  
  
 `Double` является наиболее эффективным среди дробных типов данных, поскольку процессоры на современных платформах выполняют операции с числами с плавающей запятой с двойной точностью.  Однако операции с типом `Double` имеют меньшую производительность по сравнению с целочисленными типами, такими как `Integer`.  
  
## Указание типа данных  
 Используйте [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) для объявления переменной с указанием типа.  Можно одновременно указать уровень доступа для переменной с помощью ключевых слов [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) или [Private](../../../../visual-basic/language-reference/modifiers/private.md), как показано в следующем примере.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## Преобразование знаков  
 Функции `AscW` и `ChrW` выполняются в Юникоде.  Предпочтительнее использовать их, а не `Asc` и `Chr`, которые должны преобразовывать в Юникод и из него.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Числовые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Использование технологии IntelliSense](/visual-studio/ide/using-intellisense)