---
title: "Общие сведения о компоненте ErrorProvider (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a><span data-ttu-id="7c95d-102">Общие сведения о компоненте ErrorProvider (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7c95d-102">ErrorProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="7c95d-103">Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) компонент используется для проверки пользовательского ввода в форме или элементе управления.</span><span class="sxs-lookup"><span data-stu-id="7c95d-103">The Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) component is used to validate user input on a form or control.</span></span> <span data-ttu-id="7c95d-104">Обычно используется в сочетании с проверка пользовательского ввода в форме или отображение ошибок в наборе данных.</span><span class="sxs-lookup"><span data-stu-id="7c95d-104">It is typically used in conjunction with validating user input on a form, or displaying errors within a dataset.</span></span> <span data-ttu-id="7c95d-105">Использование поставщика ошибок — лучшую альтернативу по сравнению с сообщением об ошибке в окне сообщения, так как после закрытия этого окна сообщения сообщение об ошибке больше не отображается.</span><span class="sxs-lookup"><span data-stu-id="7c95d-105">An error provider is a better alternative than displaying an error message in a message box, because once a message box is dismissed, the error message is no longer visible.</span></span> <span data-ttu-id="7c95d-106"><xref:System.Windows.Forms.ErrorProvider> Компонент отображает значок ошибки (![значок ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) рядом с соответствующим элементом управления, например текстовое поле; при наведении указателя мыши на значок ошибки появляется подсказка, показывающая строка сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7c95d-106">The <xref:System.Windows.Forms.ErrorProvider> component displays an error icon (![ErrorProvider icon](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) next to the relevant control, such as a text box; when the user positions the mouse pointer over the error icon, a ToolTip appears, showing the error message string.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="7c95d-107">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="7c95d-107">Key Properties</span></span>  
 <span data-ttu-id="7c95d-108"><xref:System.Windows.Forms.ErrorProvider> Ключевые свойства компонента — <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, и <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c95d-108">The <xref:System.Windows.Forms.ErrorProvider> component's key properties are <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, and <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span></span> <span data-ttu-id="7c95d-109">При использовании <xref:System.Windows.Forms.ErrorProvider> компонент с привязкой к данным элементы управления, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойство должно быть присвоено подходящего контейнера (как правило, форма Windows) в порядке для компонента, чтобы отобразить значок ошибки в форме.</span><span class="sxs-lookup"><span data-stu-id="7c95d-109">When using <xref:System.Windows.Forms.ErrorProvider> component with data-bound controls, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property must be set to the appropriate container (usually the Windows Form) in order for the component to display an error icon on the form.</span></span> <span data-ttu-id="7c95d-110">При добавлении компонента в конструкторе <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> свойству форме; при добавлении элемента управления в коде необходимо задать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="7c95d-110">When the component is added in the designer, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property is set to the containing form; if you add the control in code, you must set it yourself.</span></span>  
  
 <span data-ttu-id="7c95d-111"><xref:System.Windows.Forms.ErrorProvider.Icon%2A> Может быть установлено на значок пользовательской ошибки вместо значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7c95d-111">The <xref:System.Windows.Forms.ErrorProvider.Icon%2A> property can be set to a custom error icon instead of the default.</span></span> <span data-ttu-id="7c95d-112">Когда <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> свойство задано, <xref:System.Windows.Forms.ErrorProvider> компонент может отображать сообщения об ошибках для набора данных.</span><span class="sxs-lookup"><span data-stu-id="7c95d-112">When the <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> property is set, the <xref:System.Windows.Forms.ErrorProvider> component can display error messages for a dataset.</span></span> <span data-ttu-id="7c95d-113">Основной метод <xref:System.Windows.Forms.ErrorProvider> компонент является <xref:System.Windows.Forms.ErrorProvider.SetError%2A> метод, который указывает строка сообщения об ошибке и где должен отображаться значок ошибки.</span><span class="sxs-lookup"><span data-stu-id="7c95d-113">The key method of the <xref:System.Windows.Forms.ErrorProvider> component is the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method, which specifies the error message string and where the error icon should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c95d-114"><xref:System.Windows.Forms.ErrorProvider> Компонент не предоставляет встроенную поддержку для клиентами специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="7c95d-114">The <xref:System.Windows.Forms.ErrorProvider> component does not provide built-in support for accessibility clients.</span></span> <span data-ttu-id="7c95d-115">Чтобы сделать приложение доступным при использовании этого компонента, необходимо предоставить отзыв дополнительные, доступный механизм.</span><span class="sxs-lookup"><span data-stu-id="7c95d-115">To make your application accessible when using this component, you must provide an additional, accessible feedback mechanism.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c95d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7c95d-116">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider>  
 [<span data-ttu-id="7c95d-117">Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c95d-117">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [<span data-ttu-id="7c95d-118">Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c95d-118">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
