---
title: Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956078"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="3d60a-102">Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="3d60a-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="3d60a-103">С помощью компонента <xref:System.Windows.Forms.BindingSource> одни и те же данные можно легко использовать в нескольких формах.</span><span class="sxs-lookup"><span data-stu-id="3d60a-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="3d60a-104">Например, может потребоваться отобразить одну форму только для чтения со сводкой данных и другую редактируемую форму с подробными сведениями о выбранном в данный момент элементе в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="3d60a-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="3d60a-105">В этом примере демонстрируется такая возможность.</span><span class="sxs-lookup"><span data-stu-id="3d60a-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d60a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3d60a-106">Example</span></span>  
 <span data-ttu-id="3d60a-107">В примере кода ниже показано, как совместно использовать источник <xref:System.Windows.Forms.BindingSource> и связанные с ним данные в разных формах.</span><span class="sxs-lookup"><span data-stu-id="3d60a-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="3d60a-108">В этом примере общий источник <xref:System.Windows.Forms.BindingSource> передается в конструктор дочерней формы.</span><span class="sxs-lookup"><span data-stu-id="3d60a-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="3d60a-109">Дочерняя форма позволяет пользователю изменять данные элемента, выбранного в настоящий момент в главной форме.</span><span class="sxs-lookup"><span data-stu-id="3d60a-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d60a-110">В этом примере обрабатывается событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для компонента <xref:System.Windows.Forms.BindingSource>, обеспечивая синхронизацию двух форм.</span><span class="sxs-lookup"><span data-stu-id="3d60a-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="3d60a-111">Дополнительные сведения о том, почему это сделано, см [. в разделе как Убедитесь, что несколько элементов управления, привязанных к одному](../multiple-controls-bound-to-data-source-synchronized.md)источнику данных, остаются синхронизированными.</span><span class="sxs-lookup"><span data-stu-id="3d60a-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d60a-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3d60a-112">Compiling the Code</span></span>  
 <span data-ttu-id="3d60a-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3d60a-113">This example requires:</span></span>  
  
- <span data-ttu-id="3d60a-114">Ссылки на сборки System, System.Windows.Forms, System.Drawing, System.Data и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="3d60a-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d60a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3d60a-115">See also</span></span>

- [<span data-ttu-id="3d60a-116">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="3d60a-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="3d60a-117">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d60a-117">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="3d60a-118">Практическое руководство. Обработку ошибок и исключений, происходящих с DataBinding</span><span class="sxs-lookup"><span data-stu-id="3d60a-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
