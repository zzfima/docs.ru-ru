---
title: Практическое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: e5ba42c2ff86f46e2722d0f4455c10ab7b85af1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204657"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ffa4a-102">Практическое руководство. Обработка ошибок, связанных с вводом данных с помощью элемента управления DataGridView, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffa4a-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ffa4a-103">В примере кода ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DataGridView> для сообщения пользователю об ошибках ввода данных.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="ffa4a-104">Полное описание этого примера кода, см. в разделе [Пошаговое руководство: Обработка ошибок, возникающих во время ввода данных в Windows Forms элемента управления DataGridView](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span><span class="sxs-lookup"><span data-stu-id="ffa4a-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffa4a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="ffa4a-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ffa4a-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ffa4a-106">Compiling the Code</span></span>  
 <span data-ttu-id="ffa4a-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ffa4a-107">This example requires:</span></span>  
  
-   <span data-ttu-id="ffa4a-108">ссылки на сборки System, System.Data, System.Windows.Forms и System.XML.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="ffa4a-109">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ffa4a-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ffa4a-110">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ffa4a-111">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ffa4a-111">.NET Framework Security</span></span>  
 <span data-ttu-id="ffa4a-112">Хранение конфиденциальных сведений (например, пароля) в строке подключения может повлиять на безопасность приложения.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-112">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="ffa4a-113">Использование проверки подлинности Windows (также называемой встроенными средствами безопасности) — более безопасный способ управления доступом к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ffa4a-113">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="ffa4a-114">Дополнительные сведения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="ffa4a-114">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa4a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ffa4a-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="ffa4a-116">Пошаговое руководство: Обработка ошибок, возникающих во время ввода данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffa4a-116">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="ffa4a-117">Ввод данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffa4a-117">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ffa4a-118">Пошаговое руководство: Проверка данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ffa4a-118">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ffa4a-119">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="ffa4a-119">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
