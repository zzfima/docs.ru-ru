---
title: Как выполнить Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 12410e2abd1031f7ac42bdaab4b8e09a6b8b6006
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649587"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="df0bc-102">Как выполнить Создание элемента управления, имеющего клавишу доступа и поддерживающего перенос текста</span><span class="sxs-lookup"><span data-stu-id="df0bc-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="df0bc-103">В этом примере показано, как создать элемент управления, который имеет клавишу доступа и поддерживает обтекание текстом.</span><span class="sxs-lookup"><span data-stu-id="df0bc-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="df0bc-104">В примере используется <xref:System.Windows.Controls.Label> управления для демонстрации этих понятий.</span><span class="sxs-lookup"><span data-stu-id="df0bc-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df0bc-105">Пример</span><span class="sxs-lookup"><span data-stu-id="df0bc-105">Example</span></span>  
 <span data-ttu-id="df0bc-106">**Добавление обтекания текстом для метки**</span><span class="sxs-lookup"><span data-stu-id="df0bc-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="df0bc-107"><xref:System.Windows.Controls.Label> Управления не поддерживает обтекание текстом.</span><span class="sxs-lookup"><span data-stu-id="df0bc-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="df0bc-108">Если нужна метка, которая охватывает несколько строк, то можно вложить другой элемент, который поддерживает обтекание текстом, и поместить этот элемент внутрь метки.</span><span class="sxs-lookup"><span data-stu-id="df0bc-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="df0bc-109">В следующем примере показано, как использовать <xref:System.Windows.Controls.TextBlock> для создания метки, которая охватывает несколько строк текста.</span><span class="sxs-lookup"><span data-stu-id="df0bc-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="df0bc-110">**Добавление клавиши доступа и обтекания текстом в метку**</span><span class="sxs-lookup"><span data-stu-id="df0bc-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="df0bc-111">Если вам нужна <xref:System.Windows.Controls.Label> , имеет клавишу доступа (назначенную), используйте <xref:System.Windows.Controls.AccessText> элемент, который находится внутри <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="df0bc-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="df0bc-112">Элементы управления, например <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, и <xref:System.Windows.Controls.GroupBox> имеют шаблоны элементов управления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="df0bc-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="df0bc-113">Эти шаблоны содержат <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="df0bc-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="df0bc-114">Одно из свойств, которые можно установить на <xref:System.Windows.Controls.ContentPresenter> является <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= «true», который можно использовать для указания клавиши доступа для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="df0bc-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="df0bc-115">В следующем примере показано, как создать <xref:System.Windows.Controls.Label> который имеет клавишу доступа и поддерживает обтекание текстом.</span><span class="sxs-lookup"><span data-stu-id="df0bc-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="df0bc-116">Чтобы включить обтекание текстом, в примере задается <xref:System.Windows.Controls.AccessText.TextWrapping%2A> свойство и использует знак подчеркивания для указания клавиши доступа.</span><span class="sxs-lookup"><span data-stu-id="df0bc-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="df0bc-117">(Символ, который следует сразу за символом подчеркивания, является клавишей доступа).</span><span class="sxs-lookup"><span data-stu-id="df0bc-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="df0bc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="df0bc-118">See also</span></span>
- [<span data-ttu-id="df0bc-119">Практическое руководство. Установка целевого свойства метки</span><span class="sxs-lookup"><span data-stu-id="df0bc-119">How to: Set the Target Property of a Label</span></span>](https://msdn.microsoft.com/library/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)
