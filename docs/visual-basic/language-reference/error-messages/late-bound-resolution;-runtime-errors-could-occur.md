---
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
Объект присваивается переменной, объявленной [тип данных объекта](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 При объявлении переменной как `Object`, компилятор должен осуществить *позднего связывания*, что вызывает дополнительные операции во время выполнения. Это также подвергает приложение риску возникновения ошибок времени выполнения. Например, если назначить <xref:System.Windows.Forms.Form> для `Object` переменной и попытаться получить доступ к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойства, среда выполнения создает <xref:System.MemberAccessException> из-за <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.  
  
 При объявлении переменной определенного типа, компилятор может выполнять *раннее связывание* во время компиляции. Это позволяет повысить производительность, управляемого доступа к членам определенного типа и удобочитаемости кода.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42017  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если это возможно объявите переменную определенного типа.  
  
## <a name="see-also"></a>См. также  
 [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
