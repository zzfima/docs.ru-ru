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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла
Диалоговые окна открытия и сохранения по умолчанию в Windows Vista имеют область в левой части диалогового окна под названием **Избранные ссылки**. Это область пользовательских размещений. Классы <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> позволяют добавлять папки в коллекцию <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>.  
  
> [!NOTE]
> Чтобы пользовательское место отображалось в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, свойству <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> должно быть присвоено значение `true` (значение по умолчанию).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Добавление пользовательского размещения в диалоговое окно сохранения или открытия файла  
  
- Добавьте путь, идентификатор GUID известной папки или объект <xref:System.Windows.Forms.FileDialogCustomPlace> в коллекцию <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> диалогового окна.  
  
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
