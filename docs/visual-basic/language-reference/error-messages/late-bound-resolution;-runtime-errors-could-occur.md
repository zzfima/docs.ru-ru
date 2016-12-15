---
title: "Разрешение позднего связывания; возможно возникновение ошибок времени выполнения | Microsoft Docs"
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
  - "vbc42017"
  - "BC42017"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42017"
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объект присваивается переменной, объявленной как [Тип данных Object](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 При объявлении переменной в качестве `Object`, компилятор должен выполнить *позднее связывание*, вызывающее дополнительные операции во время выполнения.  Коме того, возможно возникновение ошибок времени выполнения.  Например, если присвоить значение <xref:System.Windows.Forms.Form> переменной типа `Object` и попытаться получить доступ к свойству <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>, среда выполнения создаст исключение <xref:System.MemberAccessException>, так как класс <xref:System.Windows.Forms.Form> не предоставляет свойства `NameTable`.  
  
 Если объявить переменную с определенным типом, компилятор может выполнять *раннее связывание* во время компиляции.  Это приводит к повышению производительности, управляемому доступу к членам указанного типа и лучшей читаемости кода.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42017  
  
### Чтобы исправить эту ошибку  
  
-   Если возможно, объявите переменную с определенным типом.  
  
## См. также  
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [Объявление переменных объектов](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)