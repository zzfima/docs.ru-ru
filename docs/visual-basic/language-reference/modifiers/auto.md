---
title: "Auto (Visual Basic) | Microsoft Docs"
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
  - "vb.Auto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Auto - ключевое слово"
  - "Auto - ключевое слово, внешние ссылки"
  - "Auto - ключевое слово, маршалинг строк"
  - "Declare - оператор, маршалинг строк"
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Auto (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет, что Visual Basic должен упаковывать строки согласно правилам .NET Framework, основанным на объявлении внешнего имени внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, компилятор Visual Basic не имеет доступа к данным, необходимым для корректного вызова процедуры.  Эта информация включает расположение процедуры, ее идентификатор, последовательность вызова и тип возвращаемого значения, а также используемую кодировку.  С помощью оператора [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создается ссылка на внешнюю процедуру и предоставляется необходимая информация.  
  
 Часть `charsetmodifier` в операторе `Declare` предоставляет сведения о кодировке для упаковки строк в процессе вызова внешней процедуры.  Она также влияет на то, как в Visual Basic выполняется поиск имени внешней процедуры во внешнем файле.  Модификатор `Auto` указывает, что Visual Basic будет упаковывать строки согласно правилам .NET Framework, определять базовую кодировку платформы времени выполнения и, возможно, изменять имя внешней процедуры при сбое начального поиска.  Дополнительные сведения см. в части "Кодировки" раздела [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md).  
  
 Если не указан модификатор кодировки, по умолчанию используется модификатор `Ansi`.  
  
## Заметки  
 Модификатор `Auto` можно использовать в следующем контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Примечания для разработчиков приложений смарт\-устройств  
 Это ключевое слово не поддерживается.  
  
## См. также  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)