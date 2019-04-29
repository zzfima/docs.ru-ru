---
title: Параметру Encoding нельзя присвоить значение Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970330"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Параметру Encoding нельзя присвоить значение Nothing
Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.  
  
 <xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл. Кодировка по умолчанию — UTF-8.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Предоставьте допустимое значение для параметра `encoding` .  
  
## <a name="see-also"></a>См. также

- [Кодировки файлов](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [Чтение из файлов](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Запись в файлы](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
