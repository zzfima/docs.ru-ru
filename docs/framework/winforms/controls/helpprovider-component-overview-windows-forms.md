---
title: Общие сведения о компоненте HelpProvider
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738727"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="5bc66-102">Общие сведения о компоненте HelpProvider (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5bc66-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="5bc66-103">Компонент Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) используется для связывания файла справки HTML Help 1. x (либо файла. chm, созданного с помощью справки HTML или файла. htm) с приложением Windows.</span><span class="sxs-lookup"><span data-stu-id="5bc66-103">The Windows Forms [HelpProvider](helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="5bc66-104">Получить справку можно различными способами:</span><span class="sxs-lookup"><span data-stu-id="5bc66-104">You can provide help in a variety of ways:</span></span>  
  
- <span data-ttu-id="5bc66-105">Предоставьте контекстную справку для элементов управления на Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bc66-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
- <span data-ttu-id="5bc66-106">Предоставить контекстную справку по конкретному диалоговому окну или определенным элементам управления в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5bc66-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
- <span data-ttu-id="5bc66-107">Открытие файла справки для конкретных областей, например главной страницы оглавления, индекса или функции поиска.</span><span class="sxs-lookup"><span data-stu-id="5bc66-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="5bc66-108">Использование поставщика справки</span><span class="sxs-lookup"><span data-stu-id="5bc66-108">Using the Help Provider</span></span>  
 <span data-ttu-id="5bc66-109">Добавление <xref:System.Windows.Forms.HelpProvider> компонента в форму Windows Forms позволяет другим элементам управления в форме предоставлять свойства справки компонента <xref:System.Windows.Forms.HelpProvider>.</span><span class="sxs-lookup"><span data-stu-id="5bc66-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="5bc66-110">Это позволяет предоставить справку для элементов управления в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bc66-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="5bc66-111">Файл справки можно связать с компонентом <xref:System.Windows.Forms.HelpProvider> с помощью свойства <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc66-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="5bc66-112">Вы указываете тип справки, предоставленный при вызове <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>, и предоставляя значение из перечисления <xref:System.Windows.Forms.HelpNavigator> для указанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bc66-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="5bc66-113">Вы предоставляете ключевое слово или раздел для справки, вызывая метод <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc66-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="5bc66-114">Кроме того, чтобы связать определенную строку справки с другим элементом управления, используйте метод <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc66-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="5bc66-115">Строка, связываемая с элементом управления с помощью этого метода, отображается во всплывающем окне, когда пользователь нажимает клавишу F1, когда элемент управления находится в фокусе.</span><span class="sxs-lookup"><span data-stu-id="5bc66-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="5bc66-116">Если <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> не задано, для предоставления текста справки необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bc66-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="5bc66-117">Если заданы как <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>, так и строка справки, то Справка на основе <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> будет иметь приоритет.</span><span class="sxs-lookup"><span data-stu-id="5bc66-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bc66-118">При указании пути к файлу справки в методе <xref:System.Windows.Forms.Help.ShowHelp%2A> или <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> свойства элемента управления <xref:System.Windows.Forms.HelpProvider> могут возникнуть проблемы с использованием относительного пути.</span><span class="sxs-lookup"><span data-stu-id="5bc66-118">You may encounter problems using the relative path when specifying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="5bc66-119">Поэтому для указания файла справки следует использовать абсолютный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="5bc66-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc66-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5bc66-120">See also</span></span>

- [<span data-ttu-id="5bc66-121">Справочные системы в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bc66-121">Help Systems in Windows Forms Applications</span></span>](../advanced/help-systems-in-windows-forms-applications.md)
