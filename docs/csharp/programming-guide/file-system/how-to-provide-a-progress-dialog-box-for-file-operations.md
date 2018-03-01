---
title: "Практическое руководство. Предоставление диалогового окна \"Ход выполнения\" для операций с файлами (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0ac68b5aa6014db87b4f7a269ef73d0608371bd8
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="9915a-102">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9915a-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="9915a-103">Вы можете предоставить стандартное диалоговое окно, в котором будет отображаться ход выполнения операций с файлами в Windows, при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> из пространства имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9915a-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="9915a-104">Добавление ссылки в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9915a-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="9915a-105">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="9915a-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="9915a-106">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="9915a-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="9915a-107">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="9915a-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="9915a-108">В списке имен установите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9915a-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9915a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9915a-109">Example</span></span>  
 <span data-ttu-id="9915a-110">Следующий код копирует каталог, указанный `sourcePath`, в каталог, указанный `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="9915a-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="9915a-111">Этот код также предоставляет стандартное диалоговое окно, в котором отображается примерное время, оставшееся до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="9915a-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9915a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9915a-112">See Also</span></span>  
 [<span data-ttu-id="9915a-113">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9915a-113">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
