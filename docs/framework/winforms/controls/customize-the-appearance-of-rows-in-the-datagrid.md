---
title: Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 107ec75257907b934412d9ee333b00d5df05a99c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011445"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="33d7a-102">Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33d7a-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="33d7a-103">Внешним видом строк <xref:System.Windows.Forms.DataGridView> можно управлять при помощи одного или обоих событий <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33d7a-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="33d7a-104">Эти события спроектированы таким образом, что вы можете отобразить только необходимое, позволяя отрисовать остальное элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="33d7a-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="33d7a-105">Например, для рисования пользовательского фона можно обрабатывать событие <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> и дать возможность отдельным ячейкам нарисовать собственное содержимое переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d7a-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="33d7a-106">Кроме того, можно дать возможность ячейкам отрисовать себя и добавить настраиваемый основной цвет в обработчике событий <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33d7a-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="33d7a-107">Также можно отключить прорисовку ячеек и самостоятельно нарисовать все в обработчике событий <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="33d7a-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="33d7a-108">В следующем примере кода реализованы обработчики для обоих событий, чтобы обеспечить выбор градиентного фона и настраиваемого основного цвета для нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="33d7a-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33d7a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="33d7a-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33d7a-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="33d7a-110">Compiling the Code</span></span>  
 <span data-ttu-id="33d7a-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="33d7a-111">This example requires:</span></span>  
  
- <span data-ttu-id="33d7a-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="33d7a-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="33d7a-113">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="33d7a-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="33d7a-114">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="33d7a-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="33d7a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="33d7a-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="33d7a-116">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33d7a-116">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="33d7a-117">Архитектура элементов управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="33d7a-117">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
