---
title: "Юникод (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Unicode"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Declare - оператор, маршалинг строк"
  - "Unicode - ключевое слово"
  - "Юникод, внешние ссылки"
  - "Юникод, маршалинг строк"
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Юникод (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает на то, что в Visual Basic необходимо преобразовать все строки в Юникод независимо от имени внешней объявляемой процедуры.  
  
 При вызове процедуры, определенной вне проекта, компилятор Visual Basic не имеет доступа к информации, необходимой для правильного вызова процедуры.  Эта информация включает расположение процедуры, ее идентификатор, последовательность вызова и тип возвращаемого значения, а также используемую кодировку.  С помощью оператора [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создается ссылка на внешнюю процедуру и предоставляется необходимая информация.  
  
 Часть `charsetmodifier` в операторе `Declare` содержит сведения о кодировке для упаковки строк во время вызова внешней процедуры.  Она также влияет на то, как в Visual Basic выполняется поиск имени внешней процедуры во внешнем файле.  Модификатор `Unicode` указывает, что в Visual Basic необходимо упаковать все строки в значения Юникод и найти процедуру, не изменяя ее имени в процессе поиска.  
  
 Если не указан модификатор кодировки, по умолчанию используется модификатор `Ansi`.  
  
## Заметки  
 Модификатор `Unicode` можно использовать в следующем контексте:  
  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## Примечания для разработчиков приложений смарт\-устройств  
 Это ключевое слово не поддерживается.  
  
## См. также  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)   
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)