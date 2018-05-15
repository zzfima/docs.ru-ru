---
title: Практическое руководство. Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], just-in-time data loading
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- just-in-time data loading
- DataGridView control [Windows Forms], large data sets
- virtual mode [Windows Forms], just-in-time data loading
ms.assetid: 33825f92-7a22-40ee-86d9-9a2ed1ead7b7
ms.openlocfilehash: 9e70596e212a51bc464c51f162aa1aff5e3aa0dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-virtual-mode-with-just-in-time-data-loading-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b34d9-102">Практическое руководство. Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b34d9-102">How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b34d9-103">В примере кода ниже показано, как использовать виртуальный режим в элементе управления <xref:System.Windows.Forms.DataGridView> с кэшем данных, который подгружает данные с сервера только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="b34d9-103">The following code example shows how to use virtual mode in the <xref:System.Windows.Forms.DataGridView> control with a data cache that loads data from a server only when it is needed.</span></span> <span data-ttu-id="b34d9-104">В этом примере подробно описывается в [реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="b34d9-104">This example is described in detail in [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b34d9-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b34d9-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/CS/lazyloading.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.Virtual_lazyloading#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.Virtual_lazyloading/VB/lazyloading.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b34d9-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b34d9-106">Compiling the Code</span></span>  
 <span data-ttu-id="b34d9-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b34d9-107">This example requires:</span></span>  
  
-   <span data-ttu-id="b34d9-108">ссылки на сборки System, System.Data, System.Windows.Forms и System.XML;</span><span class="sxs-lookup"><span data-stu-id="b34d9-108">References to the System, System.Data, System.Xml, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="b34d9-109">доступ к серверу SQL Server с установленным образцом базы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="b34d9-109">Access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
 <span data-ttu-id="b34d9-110">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b34d9-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b34d9-111">Можно также построить этот пример, в Visual Studio, вставив код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="b34d9-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b34d9-112">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b34d9-112">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b34d9-113">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b34d9-113">.NET Framework Security</span></span>  
 <span data-ttu-id="b34d9-114">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="b34d9-114">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="b34d9-115">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="b34d9-115">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="b34d9-116">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="b34d9-116">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34d9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b34d9-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 [<span data-ttu-id="b34d9-118">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b34d9-118">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="b34d9-119">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b34d9-119">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b34d9-120">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b34d9-120">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)
