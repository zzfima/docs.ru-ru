---
title: "Переменная &lt;имяПеременной&gt; используется до того, как ей присвоено значение | Microsoft Docs"
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
  - "vbc42104"
  - "BC42104"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42104"
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменная &lt;имяПеременной&gt; используется до того, как ей присвоено значение
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Переменная \<ИмяПеременной\> была использована прежде чем ей было присвоено значение.Пустая ссылка исключений могла получить результат во время выполнения.  
  
 Приложение всегда считывает значение переменной перед любым изменением ее значения.  
  
 Если переменной никогда не присваивали значение, она содержит значение по умолчанию для ее типа данных.  Для типа данных ссылки значение по умолчанию — [Nothing](../../../visual-basic/language-reference/nothing.md).  Чтение переменной ссылки, которая имеет значение `Nothing` может вызвать <xref:System.NullReferenceException> в некоторых случаях.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений и их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC42104  
  
### Чтобы исправить эту ошибку  
  
-   Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение перед тем как управление будет передано любой инструкции, считывающей ее.  
  
-   Одним из способов всегда гарантировать допустимость значения переменной является выполнение инициализации как части объявления.  См. в подразделе "Инициализация" раздела [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Объявление переменной](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Устранение неполадок, связанных с переменными](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)