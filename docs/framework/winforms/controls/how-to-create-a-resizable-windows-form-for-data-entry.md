---
title: Практическое руководство. Создание в Windows Forms формы для ввода данных, размер которой можно изменять
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: aeab1b506b9ded4c3c2ab527f07a8655a44cad2b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396027"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="f4c49-102">Практическое руководство. Создание в Windows Forms формы для ввода данных, размер которой можно изменять</span><span class="sxs-lookup"><span data-stu-id="f4c49-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="f4c49-103">Удачно сконструированный макет должен реагировать на изменение размеров родительской формы.</span><span class="sxs-lookup"><span data-stu-id="f4c49-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="f4c49-104">Для согласованного изменения размера и положения элементов управления на макете формы при изменении размеров формы можно использовать элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="f4c49-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="f4c49-105">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> также полезен в случаях, когда изменение содержимого элементов управления приводит к изменению макета.</span><span class="sxs-lookup"><span data-stu-id="f4c49-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="f4c49-106">Процесс, описанный в этой процедуре, можно выполнить в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f4c49-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="f4c49-107">См. также [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f4c49-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4c49-108">Пример</span><span class="sxs-lookup"><span data-stu-id="f4c49-108">Example</span></span>  
 <span data-ttu-id="f4c49-109">В следующем примере демонстрируется использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для построения макета, который соответствующим образом меняется при изменении пользователем размера формы.</span><span class="sxs-lookup"><span data-stu-id="f4c49-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="f4c49-110">Он также демонстрирует, как макет учитывает будущую локализацию.</span><span class="sxs-lookup"><span data-stu-id="f4c49-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f4c49-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f4c49-111">Compiling the Code</span></span>  
 <span data-ttu-id="f4c49-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f4c49-112">This example requires:</span></span>  
  
- <span data-ttu-id="f4c49-113">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f4c49-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c49-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f4c49-114">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="f4c49-115">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="f4c49-115">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="f4c49-116">Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="f4c49-116">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
