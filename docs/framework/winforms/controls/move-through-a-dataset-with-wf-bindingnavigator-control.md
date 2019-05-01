---
title: Практическое руководство. Перемещение по набору данных с помощью элемента управления BindingNavigator в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: d76c2e5882c9df94674294da00ba446dfbfd2b3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012741"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="d7f37-102">Практическое руководство. Перемещение по набору данных с помощью элемента управления BindingNavigator в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7f37-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="d7f37-103">При создании управляемых данными приложений часто необходимо показывать коллекции данных пользователям.</span><span class="sxs-lookup"><span data-stu-id="d7f37-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="d7f37-104">Элемент управления <xref:System.Windows.Forms.BindingNavigator> в сочетании с компонентом <xref:System.Windows.Forms.BindingSource> обеспечивает удобное и расширяемое решение для перемещения по коллекции и последовательного отображения элементов.</span><span class="sxs-lookup"><span data-stu-id="d7f37-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f37-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d7f37-105">Example</span></span>  
 <span data-ttu-id="d7f37-106">В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.BindingNavigator> для перемещения по данным.</span><span class="sxs-lookup"><span data-stu-id="d7f37-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="d7f37-107">Набор содержится в элементе <xref:System.Data.DataView>, который привязан к элементу управления <xref:System.Windows.Forms.TextBox> с компонентом <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="d7f37-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7f37-108">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="d7f37-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d7f37-109">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="d7f37-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d7f37-110">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d7f37-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7f37-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d7f37-111">Compiling the Code</span></span>  
 <span data-ttu-id="d7f37-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d7f37-112">This example requires:</span></span>  
  
- <span data-ttu-id="d7f37-113">ссылки на сборки System, System.Data, System.Drawing, System.Windows.Forms и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="d7f37-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="d7f37-114">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d7f37-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d7f37-115">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="d7f37-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f37-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d7f37-116">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d7f37-117">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="d7f37-117">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="d7f37-118">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="d7f37-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d7f37-119">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="d7f37-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
