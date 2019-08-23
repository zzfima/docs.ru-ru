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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Как Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла
Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**. Это область пользовательских размещений. Классы <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> и <xref:System.Windows.Forms.SaveFileDialog> позволяют добавлять папки в коллекцию.  
  
> [!NOTE]
> Чтобы <xref:System.Windows.Forms.OpenFileDialog> пользовательское место отображалось в или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство должно иметь значение `true` (по умолчанию).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла  
  
- Добавьте путь, идентификатор GUID известной папки или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> в коллекцию диалогового окна.  
  
     В следующем примере кода демонстрируется добавление пути.  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла](known-folder-guids-for-file-dialog-custom-places.md)
