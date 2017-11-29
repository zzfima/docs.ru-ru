---
title: "Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3ed7138c142a83584ecd19ccaebe0e31e421ce3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="53d4f-102">Практическое руководство. Поиск данных в элементе управления DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="53d4f-102">How to: Search Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="53d4f-103">При использовании <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления, который содержит много записей, может потребоваться предоставить пользователям возможность поиска определенной записи.</span><span class="sxs-lookup"><span data-stu-id="53d4f-103">When you are using a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control that contains many records, you may want to let users search for a specific record.</span></span> <span data-ttu-id="53d4f-104">Вместо того, чтобы искать данные в самом элементе управления, можно реализовать поиск, запрашивая базовый <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="53d4f-104">Rather than searching the data in the control itself, you can implement a search by querying the underlying <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="53d4f-105">Если элемент найден, можно использовать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> свойство, чтобы выбрать элемент и его прокрутку и отобразить.</span><span class="sxs-lookup"><span data-stu-id="53d4f-105">If the item is found, you can then use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> property to select the item and scroll it into view.</span></span>  
  
### <a name="to-implement-search"></a><span data-ttu-id="53d4f-106">В реализации поиска</span><span class="sxs-lookup"><span data-stu-id="53d4f-106">To implement search</span></span>  
  
1.  <span data-ttu-id="53d4f-107">Перетащите элемент управления <xref:System.Windows.Forms.TextBox> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="53d4f-107">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="53d4f-108">В окне "Свойства" измените значение свойства **Имя** на **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="53d4f-108">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="53d4f-109">Перетащите элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму, содержащую элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="53d4f-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="53d4f-110">В окне "Свойства" измените значение свойства **Имя** на **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="53d4f-110">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="53d4f-111">Задайте для свойства **Текст** значение **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="53d4f-111">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="53d4f-112">Дважды щелкните элемент управления <xref:System.Windows.Forms.Button> , чтобы открыть редактор кода, и добавьте следующий код в обработчик событий `SearchButton_Click` :</span><span class="sxs-lookup"><span data-stu-id="53d4f-112">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     <span data-ttu-id="53d4f-113">Замените *ProductsBindingSource* с именем <xref:System.Windows.Forms.BindingSource> для вашей <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>и замените *ProductID* с именем поля, которое требуется выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="53d4f-113">Replace *ProductsBindingSource* with the name of the <xref:System.Windows.Forms.BindingSource> for your <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, and replace *ProductID* with the name of the field that you want to search.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d4f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="53d4f-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="53d4f-115">Общие сведения об элементе управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="53d4f-115">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="53d4f-116">Устранение неполадок при использовании элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="53d4f-116">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="53d4f-117">Практическое руководство. Изменение внешнего вида элемента управления DataRepeater</span><span class="sxs-lookup"><span data-stu-id="53d4f-117">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
