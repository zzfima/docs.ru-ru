---
title: "Разрешение позднего связывания; Возможны ошибки времени выполнения | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ac885b0de2c4f44d4323487fc55cde9b23defa4
ms.lasthandoff: 03/13/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
Объект присваивается переменной, объявленной как [тип данных объекта](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 При объявлении переменной как `Object`, компилятор должен выполнить *позднего связывания*, которое вызывает дополнительные операции во время выполнения. Это также подвергает приложение риску возникновения ошибок времени выполнения. Например, если присвоить <xref:System.Windows.Forms.Form>для `Object` переменной и затем пытаемся обратиться к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>свойство, среда выполнения создает <xref:System.MemberAccessException>поскольку <xref:System.Windows.Forms.Form>класс не предоставляет `NameTable` свойство.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form>  
  
 При объявлении переменной определенного типа, компилятор может выполнять *раннее связывание* во время компиляции. Это позволяет повысить производительность, контролируемого доступа к членам определенного типа и лучшей читаемости кода.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42017  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если возможно объявите переменную для определенного типа.  
  
## <a name="see-also"></a>См. также  
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
