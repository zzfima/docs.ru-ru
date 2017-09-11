---
title: "Практическое руководство. Предоставление диалогового окна \"Ход выполнения\" для операций с файлами (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a43fb764e6a1ba0a2f1ad1645624c9d8a55bc858
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="4d9ed-102">Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4d9ed-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="4d9ed-103">Вы можете предоставить стандартное диалоговое окно, в котором будет отображаться ход выполнения операций с файлами в Windows, при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> из пространства имен <xref:Microsoft.VisualBasic?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="4d9ed-104">Добавление ссылки в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d9ed-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="4d9ed-105">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="4d9ed-106">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="4d9ed-107">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="4d9ed-108">В списке имен установите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d9ed-109">Пример</span><span class="sxs-lookup"><span data-stu-id="4d9ed-109">Example</span></span>  
 <span data-ttu-id="4d9ed-110">Следующий код копирует каталог, указанный `sourcePath`, в каталог, указанный `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="4d9ed-111">Этот код также предоставляет стандартное диалоговое окно, в котором отображается примерное время, оставшееся до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="4d9ed-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 <span data-ttu-id="4d9ed-112">[!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4d9ed-112">[!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9ed-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4d9ed-113">See Also</span></span>  
 [<span data-ttu-id="4d9ed-114">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4d9ed-114">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

