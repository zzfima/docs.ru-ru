---
title: Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7a6ace385f7594a467785fbc677517c8a6e1ab53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="35871-102">Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="35871-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="35871-103">Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="35871-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="35871-104">Это область пользовательских размещений.</span><span class="sxs-lookup"><span data-stu-id="35871-104">This area is called custom places.</span></span> <span data-ttu-id="35871-105"><xref:System.Windows.Forms.OpenFileDialog> И <xref:System.Windows.Forms.SaveFileDialog> классы позволяют добавлять папки для <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="35871-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35871-106">Чтобы пользовательского размещения в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойству необходимо присвоить значение `true` (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="35871-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="35871-107">Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="35871-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="35871-108">Добавьте путь к папке Известные GUID или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекцию диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="35871-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="35871-109">В следующем примере кода демонстрируется добавление пути.</span><span class="sxs-lookup"><span data-stu-id="35871-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="35871-110">См. также</span><span class="sxs-lookup"><span data-stu-id="35871-110">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="35871-111">GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла</span><span class="sxs-lookup"><span data-stu-id="35871-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
