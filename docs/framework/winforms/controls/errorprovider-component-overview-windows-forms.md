---
title: Общие сведения о компоненте ErrorProvider (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 3cfd3f306d4a18ce8a194b5197060fbca1d157d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965286"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Общие сведения о компоненте ErrorProvider (Windows Forms)
Компонент Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) используется для проверки вводимых пользователем данных в форме или элементе управления. Обычно используется в сочетании с проверкой вводимых пользователем данных в форме или отображением ошибок в наборе данных. Поставщик ошибок является лучшим вариантом, чем вывод сообщения об ошибке в окне сообщения, поскольку после закрытия окна сообщения сообщение об ошибке больше не отображается. Компонент отображает значок ошибки (![белый восклицательный знак](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)внутри красного круга) рядом с соответствующим элементом управления, например текстовым полем; когда пользователь наводит указатель мыши на значок ошибки, появляется всплывающая подсказка, <xref:System.Windows.Forms.ErrorProvider> Отображение строки сообщения об ошибке.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевыми свойствами <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>компонента являются, и <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. <xref:System.Windows.Forms.ErrorProvider> При использовании <xref:System.Windows.Forms.ErrorProvider> компонента с элементами управления <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> с привязкой к данным свойство должно быть установлено в соответствующий контейнер (обычно это форма Windows Forms), чтобы компонент отображал значок ошибки в форме. При добавлении компонента в конструктор <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойству присваивается значение, содержащееся в форме. Если элемент управления добавляется в код, его необходимо задать самостоятельно.  
  
 Для <xref:System.Windows.Forms.ErrorProvider.Icon%2A> свойства можно задать пользовательский значок ошибки вместо значения по умолчанию. Если свойство задано, компонент может отображать сообщения об ошибках для набора данных. <xref:System.Windows.Forms.ErrorProvider> <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> Ключевым методом <xref:System.Windows.Forms.ErrorProvider> компонента <xref:System.Windows.Forms.ErrorProvider.SetError%2A> является метод, который указывает строку сообщения об ошибке и место отображения значка ошибки.  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider> Компонент не предоставляет встроенную поддержку клиентов специальных возможностей. Чтобы сделать приложение доступным при использовании этого компонента, необходимо предоставить дополнительный, доступный механизм обратной связи.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ErrorProvider>
- [Практическое руководство. Просмотр ошибок в наборе данных с помощью компонента Windows Forms ErrorProvider](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Практическое руководство. Отображение значков ошибок для проверки формы с помощью компонента Windows Forms ErrorProvider](display-error-icons-for-form-validation-with-wf-errorprovider.md)
