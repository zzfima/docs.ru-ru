---
title: "Общие сведения о компоненте HelpProvider (Windows Forms)"
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
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23a9db5f7c5286eaab50f2499845f7294af878ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="1e5cf-102">Общие сведения о компоненте HelpProvider (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1e5cf-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="1e5cf-103">Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) компонент используется для связывания HTML файл справки версии 1.x (CHM-файл, созданный с помощью средства HTML Help Workshop, или HTM-файл) с приложением Windows.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-103">The Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="1e5cf-104">Можно предоставить справку в различными способами:</span><span class="sxs-lookup"><span data-stu-id="1e5cf-104">You can provide help in a variety of ways:</span></span>  
  
-   <span data-ttu-id="1e5cf-105">Предоставить контекстную справку для элементов управления в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
-   <span data-ttu-id="1e5cf-106">Предоставить контекстную справку для определенного диалогового или конкретных элементов управления в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
-   <span data-ttu-id="1e5cf-107">Откройте файл справки для конкретной области, например для главной страницы содержимое из таблицы, индекса или для функции поиска.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="1e5cf-108">С помощью поставщика справки</span><span class="sxs-lookup"><span data-stu-id="1e5cf-108">Using the Help Provider</span></span>  
 <span data-ttu-id="1e5cf-109">Добавление <xref:System.Windows.Forms.HelpProvider> компонент в форме Windows Forms позволяет других элементов управления на форме, предоставляют свойства справки <xref:System.Windows.Forms.HelpProvider> компонента.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="1e5cf-110">Это дает возможность предоставить справку для элементов управления на форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="1e5cf-111">Можно связать файл справки с <xref:System.Windows.Forms.HelpProvider> компонента с помощью <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="1e5cf-112">Укажите тип путем вызова справки <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> и указания значения из <xref:System.Windows.Forms.HelpNavigator> перечисления для указанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="1e5cf-113">Укажите ключевое слово или раздел для справки, вызвав <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="1e5cf-114">При необходимости, чтобы связать определенную строку Help с другим элементом управления, используйте <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="1e5cf-115">Строка, которая связана с элементом управления с помощью этого метода отображается во всплывающем окне при нажатии клавиши F1, когда элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="1e5cf-116">Если <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> не был задан, необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> предоставить текст справки.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="1e5cf-117">Если одновременно заданы <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> и строка справки на основе справки <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> будет иметь приоритет.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e5cf-118">Возникли проблемы с использованием относительного пути при при указании пути к файлу справки в <xref:System.Windows.Forms.Help.ShowHelp%2A> метода или <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойства <xref:System.Windows.Forms.HelpProvider> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-118">You may encounter problems using the relative path when specifiying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="1e5cf-119">Таким образом необходимо с помощью абсолютный путь к файлу справки.</span><span class="sxs-lookup"><span data-stu-id="1e5cf-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5cf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1e5cf-120">See Also</span></span>  
 [<span data-ttu-id="1e5cf-121">Справочные системы в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e5cf-121">Help Systems in Windows Forms Applications</span></span>](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
