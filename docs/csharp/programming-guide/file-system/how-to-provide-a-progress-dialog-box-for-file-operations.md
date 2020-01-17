---
title: Руководство по программированию на C#. Отображение диалогового окна хода выполнения для операций с файлами
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 30ab84054d26f5b32a3f042a8d35d5ef1211d928
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705136"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="bcf49-102">Руководство по программированию на C#. Отображение диалогового окна хода выполнения для операций с файлами</span><span class="sxs-lookup"><span data-stu-id="bcf49-102">How to provide a progress dialog box for file operations (C# Programming Guide)</span></span>
<span data-ttu-id="bcf49-103">Вы можете предоставить стандартное диалоговое окно, в котором будет отображаться ход выполнения операций с файлами в Windows, при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> из пространства имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bcf49-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="bcf49-104">Добавление ссылки в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bcf49-104">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="bcf49-105">В строке меню выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="bcf49-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="bcf49-106">Откроется диалоговое окно **Диспетчер ссылок**.</span><span class="sxs-lookup"><span data-stu-id="bcf49-106">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="bcf49-107">В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="bcf49-107">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="bcf49-108">В списке имен установите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="bcf49-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcf49-109">Пример</span><span class="sxs-lookup"><span data-stu-id="bcf49-109">Example</span></span>  
 <span data-ttu-id="bcf49-110">Следующий код копирует каталог, указанный `sourcePath`, в каталог, указанный `destinationPath`.</span><span class="sxs-lookup"><span data-stu-id="bcf49-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="bcf49-111">Этот код также предоставляет стандартное диалоговое окно, в котором отображается примерное время, оставшееся до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="bcf49-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="bcf49-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bcf49-112">See also</span></span>

- [<span data-ttu-id="bcf49-113">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="bcf49-113">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
