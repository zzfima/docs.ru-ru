---
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: af027b7752fdf13f1540010a8ddb681182c1b23c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
