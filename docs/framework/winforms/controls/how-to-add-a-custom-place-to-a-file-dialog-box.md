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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла
Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**. Это область пользовательских размещений. <xref:System.Windows.Forms.OpenFileDialog> И <xref:System.Windows.Forms.SaveFileDialog> классы позволяют добавлять папки для <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекции.  
  
> [!NOTE]
>  Чтобы пользовательского размещения в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойству необходимо присвоить значение `true` (по умолчанию).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла  
  
-   Добавьте путь к папке Известные GUID или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекцию диалоговое окно.  
  
     В следующем примере кода демонстрируется добавление пути.  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [GUID известных папок для пользовательских размещений, отображаемых в диалоговом окне открытия или сохранения файла](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
