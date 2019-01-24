---
title: 'Как выполнить: Добавление пользовательских размещений в диалоговое окно файла'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 797b98cb408c7f9fc1d55b774f7ceccef009bb22
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674652"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="d9d0b-102">Как выполнить: Добавление пользовательских размещений в диалоговое окно файла</span><span class="sxs-lookup"><span data-stu-id="d9d0b-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="d9d0b-103">Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="d9d0b-104">Это область пользовательских размещений.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-104">This area is called custom places.</span></span> <span data-ttu-id="d9d0b-105"><xref:System.Windows.Forms.OpenFileDialog> И <xref:System.Windows.Forms.SaveFileDialog> классы позволяют добавлять папки <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9d0b-106">Чтобы пользовательское размещение отображалось в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойству должно быть присвоено `true` (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d9d0b-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="d9d0b-107">Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="d9d0b-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="d9d0b-108">Добавьте путь, GUID известной папки, или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекцию диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="d9d0b-109">В следующем примере кода демонстрируется добавление пути.</span><span class="sxs-lookup"><span data-stu-id="d9d0b-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d9d0b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d9d0b-110">See also</span></span>
- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d9d0b-111">GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла</span><span class="sxs-lookup"><span data-stu-id="d9d0b-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
