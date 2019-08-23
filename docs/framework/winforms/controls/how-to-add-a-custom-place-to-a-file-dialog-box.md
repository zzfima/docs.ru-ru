---
title: Как Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 824c948fafd0a0995ad261389414d2d79918c8a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916341"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="8e65f-102">Как Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="8e65f-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="8e65f-103">Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="8e65f-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="8e65f-104">Это область пользовательских размещений.</span><span class="sxs-lookup"><span data-stu-id="8e65f-104">This area is called custom places.</span></span> <span data-ttu-id="8e65f-105">Классы <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> и <xref:System.Windows.Forms.SaveFileDialog> позволяют добавлять папки в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="8e65f-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e65f-106">Чтобы <xref:System.Windows.Forms.OpenFileDialog> пользовательское место отображалось в или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство должно иметь значение `true` (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8e65f-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="8e65f-107">Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="8e65f-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="8e65f-108">Добавьте путь, идентификатор GUID известной папки или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> в коллекцию диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="8e65f-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="8e65f-109">В следующем примере кода демонстрируется добавление пути.</span><span class="sxs-lookup"><span data-stu-id="8e65f-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8e65f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8e65f-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8e65f-111">GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла</span><span class="sxs-lookup"><span data-stu-id="8e65f-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
