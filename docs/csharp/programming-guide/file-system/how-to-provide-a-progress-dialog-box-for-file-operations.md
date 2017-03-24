---
title: "Практическое руководство. Предоставление диалогового окна &quot;Ход выполнения&quot; для операций с файлами (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "ход выполнения - диалоговое окно [C#]"
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Практическое руководство. Предоставление диалогового окна &quot;Ход выполнения&quot; для операций с файлами (Руководство по программированию на C#)
Можно предоставить стандартное диалоговое окно, показывающее ход выполнения операций с файлами в Windows при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> в пространстве имен <xref:Microsoft.VisualBasic?displayProperty=fullName>.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Добавление ссылки в Visual Studio  
  
1.  В меню **Проект** выберите **Добавить ссылку**.  
  
     Появится диалоговое окно **Диспетчер ссылок**.  
  
2.  В области **Сборки** выберите **Framework**, если она еще не выбрана.  
  
3.  В списке имен выберите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
## Пример  
 В следующем коде каталог, указанный параметром `sourcePath`, копируется в каталог, указанный параметром `destinationPath`.  Этот код также предоставляет стандартное диалоговое окно, в котором показывается оценочное время, оставшееся до окончания операции.  
  
 [!code-cs[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## См. также  
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)