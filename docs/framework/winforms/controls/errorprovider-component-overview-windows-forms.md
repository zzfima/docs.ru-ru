---
title: Общие сведения о компоненте ErrorProvider
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745788"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Общие сведения о компоненте ErrorProvider (Windows Forms)
Компонент Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) используется для проверки вводимых пользователем данных в форме или элементе управления. Обычно используется в сочетании с проверкой вводимых пользователем данных в форме или отображением ошибок в наборе данных. Поставщик ошибок является лучшим вариантом, чем вывод сообщения об ошибке в окне сообщения, поскольку после закрытия окна сообщения сообщение об ошибке больше не отображается. Компонент <xref:System.Windows.Forms.ErrorProvider> отображает значок ошибки (![белый восклицательный знак внутри красного круга.](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)) рядом с соответствующим элементом управления, например текстовым полем. Когда пользователь наводит указатель мыши на значок ошибки, появляется подсказка, отображающая строку сообщения об ошибке.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевыми свойствами компонента <xref:System.Windows.Forms.ErrorProvider> являются <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>и <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. При использовании <xref:System.Windows.Forms.ErrorProvider> компонента с элементами управления с привязкой к данным свойство <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> должно быть установлено в соответствующий контейнер (обычно это форма Windows Forms), чтобы компонент мог отобразить значок ошибки в форме. При добавлении компонента в конструктор свойству <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> присваивается содержащая его форма. Если элемент управления добавляется в код, его необходимо задать самостоятельно.  
  
 Для свойства <xref:System.Windows.Forms.ErrorProvider.Icon%2A> можно задать пользовательский значок ошибки вместо значения по умолчанию. Если задано свойство <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, компонент <xref:System.Windows.Forms.ErrorProvider> может отображать сообщения об ошибках для набора данных. Ключевым методом <xref:System.Windows.Forms.ErrorProvider> компонента является метод <xref:System.Windows.Forms.ErrorProvider.SetError%2A>, который указывает строку сообщения об ошибке и место, где должен появиться значок ошибки.  
  
> [!NOTE]
> Компонент <xref:System.Windows.Forms.ErrorProvider> не предоставляет встроенную поддержку клиентов специальных возможностей. Чтобы сделать приложение доступным при использовании этого компонента, необходимо предоставить дополнительный, доступный механизм обратной связи.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ErrorProvider>
- [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
