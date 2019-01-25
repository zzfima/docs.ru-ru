---
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 9caf02907e4b6de4c2bd8de778d4ad7a9320a82b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690583"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
Объект присваивается переменной, объявленной с [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 При объявлении переменной как `Object`, компилятор должен осуществить *позднее связывание*, что вызывает дополнительные операции во время выполнения. Это также подвергает приложение риску возникновения ошибок времени выполнения. Например, если вы назначаете <xref:System.Windows.Forms.Form> для `Object` переменной и затем пытаемся обратиться к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойство, среда выполнения создает <xref:System.MemberAccessException> поскольку <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.  
  
 Если вы объявляете переменную определенного типа, компилятор может выполнять *раннее связывание* во время компиляции. Это позволяет повысить производительность, управляемый доступ к членами определенного типа и лучшей читаемости кода.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42017  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если это возможно следует объявите переменную с определенным типом.  
  
## <a name="see-also"></a>См. также
- [Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
