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
ms.openlocfilehash: d9c1373a16f7d62c2933e01e513478fc6c9866d2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721883"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Как выполнить: Добавление пользовательских размещений в диалоговое окно файла
Диалоговые окна сохранения или открытия файла по умолчанию в [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] содержат область в левой части окна под названием **Избранные ссылки**. Это область пользовательских размещений. <xref:System.Windows.Forms.OpenFileDialog> И <xref:System.Windows.Forms.SaveFileDialog> классы позволяют добавлять папки <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекции.  
  
> [!NOTE]
>  Чтобы пользовательское размещение отображалось в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойству должно быть присвоено `true` (по умолчанию).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла  
  
-   Добавьте путь, GUID известной папки, или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекцию диалоговое окно.  
  
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
