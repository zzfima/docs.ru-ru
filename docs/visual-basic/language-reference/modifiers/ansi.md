---
title: "Ansi (Visual Basic) | Microsoft Docs"
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
  - "vb.Ansi"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ANSI"
  - "ANSI, Visual Basic"
  - "Declare - оператор, маршалинг строк"
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ansi (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, должен ли Visual Basic преобразовывать все строки к значениям ANSI независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, компилятор Visual Basic не имеет доступа к необходимым для корректного вызова процедуры данным.  Эта информация включает расположение процедуры, ее идентификатор, последовательность вызова и тип возвращаемого значения, а также используемую кодировку.  С помощью оператора [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создается ссылка на внешнюю процедуру и предоставляется необходимая информация.  
  
 Часть `charsetmodifier` в операторе `Declare` предоставляет сведения о кодировке для упаковки строк в процессе вызова внешней процедуры.  Она также влияет на то, как в Visual Basic выполняется поиск имени внешней процедуры во внешнем файле.  Модификатор `Ansi` указывает, на то, что Visual Basic должен маршалировать все строки в ANSI и должен найти процедуру, не изменяя ее имя в ходе поиска.  
  
 Если не указан модификатор кодировки, по умолчанию используется модификатор `Ansi`.  
  
## Заметки  
 Модификатор `Ansi` можно использовать в следующем контексте.  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Примечания для разработчиков приложений смарт\-устройств  
 Это ключевое слово не поддерживается.  
  
## См. также  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Юникод](../../../visual-basic/language-reference/modifiers/unicode.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)