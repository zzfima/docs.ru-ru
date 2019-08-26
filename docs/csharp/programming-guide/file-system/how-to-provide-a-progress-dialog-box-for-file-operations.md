---
title: Практическое руководство. Отображение диалогового окна хода выполнения для операций с файлами (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 028e779f3cd8a17f162a79791b0c84abae14cf44
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590053"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a>Практическое руководство. Отображение диалогового окна хода выполнения для операций с файлами (руководство по программированию на C#)
Вы можете предоставить стандартное диалоговое окно, в котором будет отображаться ход выполнения операций с файлами в Windows, при использовании метода <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> из пространства имен <xref:Microsoft.VisualBasic?displayProperty=nameWithType>.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a>Добавление ссылки в Visual Studio  
  
1. В строке меню выберите **Проект**, **Добавить ссылку**.  
  
     Откроется диалоговое окно **Диспетчер ссылок**.  
  
2. В области **Сборки** выберите **Платформа**, если этот вариант еще не выбран.  
  
3. В списке имен установите флажок **Microsoft.VisualBasic**, а затем нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
## <a name="example"></a>Пример  
 Следующий код копирует каталог, указанный `sourcePath`, в каталог, указанный `destinationPath`. Этот код также предоставляет стандартное диалоговое окно, в котором отображается примерное время, оставшееся до завершения операции.  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a>См. также

- [Файловая система и реестр (руководство по программированию на C#)](./index.md)
