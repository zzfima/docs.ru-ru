---
title: Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 0e5f856c69fab45a4c92e12746f357320d2e323c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435746"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="f2ef0-102">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="f2ef0-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="f2ef0-103">Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> .</span><span class="sxs-lookup"><span data-stu-id="f2ef0-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f2ef0-104">Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="f2ef0-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="f2ef0-105">В этом разделе показано, как последовательно искать и выделять каждое вхождение строки в содержимом элемента управления "текст" с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2ef0-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2ef0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f2ef0-106">Example</span></span>  
 <span data-ttu-id="f2ef0-107">В следующем примере получен объект <xref:System.Windows.Automation.TextPattern> из текстового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f2ef0-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="f2ef0-108">Затем объект <xref:System.Windows.Automation.Text.TextPatternRange>, представляющий текстовое содержимое всего документа, создается с помощью свойства <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> этого <xref:System.Windows.Automation.TextPattern>.</span><span class="sxs-lookup"><span data-stu-id="f2ef0-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="f2ef0-109">Затем создаются два дополнительных объекта <xref:System.Windows.Automation.Text.TextPatternRange> для последовательного поиска и выделения.</span><span class="sxs-lookup"><span data-stu-id="f2ef0-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="f2ef0-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2ef0-110">See also</span></span>

- [<span data-ttu-id="f2ef0-111">Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="f2ef0-111">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
