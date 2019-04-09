---
title: Практическое руководство. Изменение типа курсора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 5c9e6931f6addb62a51e44b06a159d4e7b1e5f8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141210"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="3e134-102">Практическое руководство. Изменение типа курсора</span><span class="sxs-lookup"><span data-stu-id="3e134-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="3e134-103">В этом примере показано, как изменить <xref:System.Windows.Input.Cursor> указателя мыши для конкретного элемента, а также для приложения.</span><span class="sxs-lookup"><span data-stu-id="3e134-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="3e134-104">В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл кода программной части.</span><span class="sxs-lookup"><span data-stu-id="3e134-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e134-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3e134-105">Example</span></span>  
 <span data-ttu-id="3e134-106">Создается пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.ComboBox> для выбора нужного <xref:System.Windows.Input.Cursor>, пару <xref:System.Windows.Controls.RadioButton> объектов, чтобы определить, если изменение курсора применяется только к одному элементу или применяется ко всему приложению и <xref:System.Windows.Controls.Border> который является элементом, применяемый к новым курсором.</span><span class="sxs-lookup"><span data-stu-id="3e134-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="3e134-107">Следующий код создает <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> обработчик событий, вызываемый при изменении типа курсора в <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="3e134-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="3e134-108">Оператор switch выполняется фильтрация по имени курсора и наборы <xref:System.Windows.FrameworkElement.Cursor%2A> свойство <xref:System.Windows.Controls.Border> с именем *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="3e134-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="3e134-109">Если задано значение «Всего приложения,» изменение курсора <xref:System.Windows.Input.Mouse.OverrideCursor%2A> свойству <xref:System.Windows.FrameworkElement.Cursor%2A> свойство <xref:System.Windows.Controls.Border> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3e134-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="3e134-110">Это заставляет курсор для изменения для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="3e134-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="3e134-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3e134-111">See also</span></span>

- [<span data-ttu-id="3e134-112">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="3e134-112">Input Overview</span></span>](input-overview.md)
