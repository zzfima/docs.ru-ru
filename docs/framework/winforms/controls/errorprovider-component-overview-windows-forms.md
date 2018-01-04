---
title: "Общие сведения о компоненте ErrorProvider (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a>Общие сведения о компоненте ErrorProvider (Windows Forms)
Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) компонент используется для проверки пользовательского ввода в форме или элементе управления. Обычно используется в сочетании с проверка пользовательского ввода в форме или отображение ошибок в наборе данных. Использование поставщика ошибок — лучшую альтернативу по сравнению с сообщением об ошибке в окне сообщения, так как после закрытия этого окна сообщения сообщение об ошибке больше не отображается. <xref:System.Windows.Forms.ErrorProvider> Компонент отображает значок ошибки (![значок ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) рядом с соответствующим элементом управления, например текстовое поле; при наведении указателя мыши на значок ошибки появляется подсказка, показывающая строка сообщения об ошибке.  
  
## <a name="key-properties"></a>Ключевые свойства  
 <xref:System.Windows.Forms.ErrorProvider> Ключевые свойства компонента — <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, и <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. При использовании <xref:System.Windows.Forms.ErrorProvider> компонент с привязкой к данным элементы управления, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойство должно быть присвоено подходящего контейнера (как правило, форма Windows) в порядке для компонента, чтобы отобразить значок ошибки в форме. При добавлении компонента в конструкторе <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойству форме; при добавлении элемента управления в коде необходимо задать самостоятельно.  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> Может быть установлено на значок пользовательской ошибки вместо значения по умолчанию. Когда <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> свойство задано, <xref:System.Windows.Forms.ErrorProvider> компонент может отображать сообщения об ошибках для набора данных. Основной метод <xref:System.Windows.Forms.ErrorProvider> компонент является <xref:System.Windows.Forms.ErrorProvider.SetError%2A> метод, который указывает строка сообщения об ошибке и где должен отображаться значок ошибки.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ErrorProvider> Компонент не предоставляет встроенную поддержку для клиентами специальных возможностей. Чтобы сделать приложение доступным при использовании этого компонента, необходимо предоставить отзыв дополнительные, доступный механизм.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ErrorProvider>  
 [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
