---
title: 'Как: Открыть файлы с компонентом OpenFileDialog'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182134"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a>Как: Открыть файлы с OpenFileDialog

Компонент <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> открывает диалоговое окно Windows для просмотра и выбора файлов. Чтобы открыть и прочитать выбранные файлы, можно использовать <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> метод <xref:System.IO.StreamReader?displayProperty=nameWithType> или создать экземпляр класса. Следующие примеры показывают оба подхода.

В рамках .NET для получения <xref:System.Windows.Forms.FileDialog.FileName%2A> или установки свойства <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> требуется уровень привилегий, предоставляемый классом. Примеры выполнить проверку разрешений <xref:System.Security.Permissions.FileIOPermission> и могут выбросить исключение из-за недостаточной привилегий, если они работают в контексте частичного доверия. Для получения дополнительной [информации](../../misc/code-access-security-basics.md)см.

Вы можете создавать и запускать эти примеры в виде приложений .NET Framework из командной строки C- или Visual Basic. Для получения дополнительной информации [см.](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)

Начиная с .NET Core 3.0, вы также можете создавать и запускать примеры приложений Windows .NET Core из папки с названием папки .NET Core Windows Forms * \<>.csproj* project file.

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a>Пример: Прочитайте файл как поток с StreamReader  
  
В следующем примере <xref:System.Windows.Forms.Button> используется обработчик <xref:System.Windows.Forms.Control.Click> событий <xref:System.Windows.Forms.OpenFileDialog> управления <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Windows Forms, чтобы открыть метод. После того, как пользователь выбирает файл и выбирает <xref:System.IO.StreamReader> **OK,** экземпляр класса читает файл и отображает его содержимое в текстовом поле формы. Для получения дополнительной информации о <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> чтении из файлов потоков, см. <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a>Пример: Откройте файл из фильтрованного выбора с помощью OpenFile

В следующем примере используется <xref:System.Windows.Forms.Control.Click> обработчик <xref:System.Windows.Forms.OpenFileDialog> событий <xref:System.Windows.Forms.Button> элемента управления для открытия фильтра, отображающего только текстовые файлы. После того, как пользователь выбирает текстовый <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> файл и выбирает **OK,** метод используется для открытия файла в блокноте.

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.OpenFileDialog>
- [Компонент OpenFileDialog](openfiledialog-component-windows-forms.md)
