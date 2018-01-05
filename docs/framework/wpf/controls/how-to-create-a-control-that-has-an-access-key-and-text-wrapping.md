---
title: "Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 428d8febe5a789f22eef97301fca3aa4b22f25b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="86730-102">Практическое руководство. Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста</span><span class="sxs-lookup"><span data-stu-id="86730-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="86730-103">В этом примере показано, как создать элемент управления, который имеет клавишу доступа и поддерживает обтекание текстом.</span><span class="sxs-lookup"><span data-stu-id="86730-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="86730-104">В этом примере <xref:System.Windows.Controls.Label> управления для иллюстрации этих основных понятий.</span><span class="sxs-lookup"><span data-stu-id="86730-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86730-105">Пример</span><span class="sxs-lookup"><span data-stu-id="86730-105">Example</span></span>  
 <span data-ttu-id="86730-106">**Добавление обтекания текстом для метки**</span><span class="sxs-lookup"><span data-stu-id="86730-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="86730-107"><xref:System.Windows.Controls.Label> Управления не поддерживает перенос текста.</span><span class="sxs-lookup"><span data-stu-id="86730-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="86730-108">Если нужна метка, которая охватывает несколько строк, то можно вложить другой элемент, который поддерживает обтекание текстом, и поместить этот элемент внутрь метки.</span><span class="sxs-lookup"><span data-stu-id="86730-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="86730-109">В следующем примере показано, как использовать <xref:System.Windows.Controls.TextBlock> для создания метки, которая содержит несколько строк текста.</span><span class="sxs-lookup"><span data-stu-id="86730-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="86730-110">**Добавление клавиши доступа и обтекания текстом в метку**</span><span class="sxs-lookup"><span data-stu-id="86730-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="86730-111">Если вам требуется <xref:System.Windows.Controls.Label> , содержащий ключ доступа (назначенную), используйте <xref:System.Windows.Controls.AccessText> элемент, находящийся внутри <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="86730-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="86730-112">Элементы управления, например <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, и <xref:System.Windows.Controls.GroupBox> есть шаблона элемента управления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86730-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="86730-113">Эти шаблоны содержат <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="86730-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="86730-114">Одно из свойств, которые можно установить на <xref:System.Windows.Controls.ContentPresenter> — <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= «true», который можно использовать для указания клавиши доступа для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="86730-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="86730-115">В следующем примере показано, как создать <xref:System.Windows.Controls.Label> , имеет клавишу доступа и поддерживает перенос текста.</span><span class="sxs-lookup"><span data-stu-id="86730-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="86730-116">Чтобы включить перенос текста, в примере задается <xref:System.Windows.Controls.AccessText.TextWrapping%2A> свойства и используется знак подчеркивания для указания ключа доступа.</span><span class="sxs-lookup"><span data-stu-id="86730-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="86730-117">(Символ, который следует сразу за символом подчеркивания, является клавишей доступа).</span><span class="sxs-lookup"><span data-stu-id="86730-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="86730-118">См. также</span><span class="sxs-lookup"><span data-stu-id="86730-118">See Also</span></span>  
 [<span data-ttu-id="86730-119">Практическое руководство. Установка целевого свойства метки</span><span class="sxs-lookup"><span data-stu-id="86730-119">How to: Set the Target Property of a Label</span></span>](http://msdn.microsoft.com/en-us/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
