---
title: Практическое руководство. Уведомление об изменении данных с использованием метода ResetItem компонента BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: bb5c05d22dd9fa47f4d1abe46acccdee19dfa38e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662315"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="85444-102">Практическое руководство. Уведомление об изменении данных с использованием метода ResetItem компонента BindingSource</span><span class="sxs-lookup"><span data-stu-id="85444-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="85444-103">Некоторые источники данных для элементов управления не инициируют уведомления об изменении при добавлении, изменении или удалении элементов.</span><span class="sxs-lookup"><span data-stu-id="85444-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="85444-104">При помощи компонента <xref:System.Windows.Forms.BindingSource> можно выполнить привязку к источникам данных и вызывать уведомление об изменениях из кода.</span><span class="sxs-lookup"><span data-stu-id="85444-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85444-105">Пример</span><span class="sxs-lookup"><span data-stu-id="85444-105">Example</span></span>  
 <span data-ttu-id="85444-106">Эта форма демонстрирует использование компонента <xref:System.Windows.Forms.BindingSource> для привязки списка к элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="85444-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="85444-107">Список не инициирует уведомления об изменениях, поэтому при изменении элемента в списке вызывается метод <xref:System.Windows.Forms.BindingSource.ResetItem%2A> из <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="85444-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="85444-108">.</span><span class="sxs-lookup"><span data-stu-id="85444-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85444-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="85444-109">Compiling the Code</span></span>  
 <span data-ttu-id="85444-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="85444-110">This example requires:</span></span>  
  
- <span data-ttu-id="85444-111">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="85444-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="85444-112">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="85444-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="85444-113">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="85444-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85444-114">См. также</span><span class="sxs-lookup"><span data-stu-id="85444-114">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="85444-115">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="85444-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="85444-116">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="85444-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
