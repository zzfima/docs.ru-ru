---
title: Практическое руководство. Связывание элемента управления с типом в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: f47090f5d0765833f7ac17a947691a4693d9923b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761355"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="0c6ae-102">Практическое руководство. Связывание элемента управления с типом в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c6ae-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="0c6ae-103">При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="0c6ae-104">Такая ситуация особенно часто возникает на этапе разработки, когда данные недоступны, но все равно нужно, чтобы элемент управления отображал данные из открытого интерфейса типа.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="0c6ae-105">Например, вы привязываете элемент управления <xref:System.Windows.Forms.DataGridView> к объекту, предоставляемому веб-службой, и хотите, чтобы во время разработки элемент управления <xref:System.Windows.Forms.DataGridView> помечал свои столбцы именами членов пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="0c6ae-106">Элемент управления можно легко привязать к типу с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c6ae-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0c6ae-107">Example</span></span>  
 <span data-ttu-id="0c6ae-108">В примере кода ниже показано, как привязать элемент управления <xref:System.Windows.Forms.DataGridView> к пользовательскому типу с помощью компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="0c6ae-109">После запуска примера можно увидеть, что <xref:System.Windows.Forms.DataGridView> пометил столбцы, отражающие свойства объекта `Customer`, перед заполнением элемента управления данными.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="0c6ae-110">В примере есть кнопка Add Customer (Добавить клиента) для добавления данных в элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0c6ae-111">При нажатии на кнопку новый объект `Customer` добавляется в <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="0c6ae-112">В реальном сценарии данные можно было бы получить путем вызова веб-службы или другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c6ae-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0c6ae-113">Compiling the Code</span></span>  
 <span data-ttu-id="0c6ae-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="0c6ae-114">This example requires:</span></span>  
  
- <span data-ttu-id="0c6ae-115">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="0c6ae-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0c6ae-116">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0c6ae-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0c6ae-117">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="0c6ae-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6ae-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0c6ae-118">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="0c6ae-119">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="0c6ae-119">BindingSource Component</span></span>](bindingsource-component.md)
