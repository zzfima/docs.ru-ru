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
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976987"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="005dc-102">Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="005dc-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="005dc-103">Диалоговые окна открытия и сохранения по умолчанию в Windows Vista имеют область в левой части диалогового окна под названием **Избранные ссылки**.</span><span class="sxs-lookup"><span data-stu-id="005dc-103">The default open and save dialog boxes on Windows Vista have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="005dc-104">Это область пользовательских размещений.</span><span class="sxs-lookup"><span data-stu-id="005dc-104">This area is called custom places.</span></span> <span data-ttu-id="005dc-105">Классы <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> позволяют добавлять папки в коллекцию <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>.</span><span class="sxs-lookup"><span data-stu-id="005dc-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="005dc-106">Чтобы пользовательское место отображалось в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, свойству <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> должно быть присвоено значение `true` (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="005dc-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="005dc-107">Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла</span><span class="sxs-lookup"><span data-stu-id="005dc-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="005dc-108">Добавьте путь, идентификатор GUID известной папки или объект <xref:System.Windows.Forms.FileDialogCustomPlace> в коллекцию <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="005dc-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="005dc-109">В следующем примере кода демонстрируется добавление пути.</span><span class="sxs-lookup"><span data-stu-id="005dc-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="005dc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="005dc-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="005dc-111">GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла</span><span class="sxs-lookup"><span data-stu-id="005dc-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
