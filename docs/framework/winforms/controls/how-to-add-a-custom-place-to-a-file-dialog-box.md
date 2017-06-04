---
title: "Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "пользовательского размещения в диалоговое окно"
  - "добавление пользовательского размещения в диалоговое окно"
  - "CustomPlaces - коллекция"
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Добавление пользовательских размещений в диалоговое окно сохранения или открытия файла
Значение по умолчанию открывать и сохранять диалоговые окна на [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] имеют область слева от под названием **Избранные ссылки**. Эта область пользовательских размещений. <xref:System.Windows.Forms.OpenFileDialog> и <xref:System.Windows.Forms.SaveFileDialog> классы позволяют добавлять папки для <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекции.  
  
> [!NOTE]
>  Чтобы пользовательского размещения в <xref:System.Windows.Forms.OpenFileDialog> или <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> свойство должно быть присвоено `true` (по умолчанию).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Добавление пользовательского размещения в диалоговое окно файла  
  
-   Добавьте путь к папке известный GUID или <xref:System.Windows.Forms.FileDialogCustomPlace> объект <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> коллекцию диалоговое окно.  
  
     В следующем примере кода демонстрируется добавление пути:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FileDialog>   
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=fullName>   
 [Известные GUID папок для пользовательских размещений диалогового окна файла](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)