---
title: Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: 7906811d5a324ba3f2bd73cc057298e007ac311b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941561"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="5c59d-102">Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="5c59d-102">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="5c59d-103">Чтобы пользователи приложения могли выбирать дату и время, которые будут отображаться в указанном формате, используйте элемент управления <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="5c59d-103">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="5c59d-104">Ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DateTimePicker> для отображения времени.</span><span class="sxs-lookup"><span data-stu-id="5c59d-104">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="5c59d-105">Отображение времени с помощью элемента управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="5c59d-105">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="5c59d-106">Задайте свойству <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение <xref:System.Windows.Forms.DateTimePickerFormat.Time></span><span class="sxs-lookup"><span data-stu-id="5c59d-106">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="5c59d-107">Присвойте свойству <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> элемента <xref:System.Windows.Forms.DateTimePicker> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5c59d-107">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="5c59d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="5c59d-108">Example</span></span>  
 <span data-ttu-id="5c59d-109">В примере кода ниже показано, как создать элемент <xref:System.Windows.Forms.DateTimePicker>, позволяющий пользователю выбирать только время.</span><span class="sxs-lookup"><span data-stu-id="5c59d-109">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c59d-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5c59d-110">Compiling the Code</span></span>  
 <span data-ttu-id="5c59d-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="5c59d-111">This example requires:</span></span>  
  
- <span data-ttu-id="5c59d-112">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5c59d-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="5c59d-113">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5c59d-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="5c59d-114">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="5c59d-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c59d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5c59d-115">See also</span></span>

- [<span data-ttu-id="5c59d-116">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="5c59d-116">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
