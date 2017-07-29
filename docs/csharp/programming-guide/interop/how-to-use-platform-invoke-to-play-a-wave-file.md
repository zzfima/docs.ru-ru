---
title: "Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 001236392d2b3d3c70dbd0faf2a899929dfe8625
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#)
В следующем примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в операционной системе Windows.  
  
## <a name="example"></a>Пример  
 В этом примере `DllImport` используется для импорта точки входа метода `PlaySound` файла `winmm.dll` как `Form1 PlaySound()`. Пример включает простую форму Windows с кнопкой. При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, позволяющее выбрать файл для воспроизведения. Выбранный WAV-файл воспроизводится с помощью метода `PlaySound()` из метода сборки winmm.dll. Дополнительные сведения о методе `PlaySound` winmm.dll см. в статье [Использование функции PlaySound со звуковыми WAV-файлами](http://go.microsoft.com/fwlink/?LinkId=148553). Найдите и выберите файл с расширением WAV и нажмите кнопку **Открыть**, чтобы воспроизвести этот WAV-файл, используя вызов неуправляемого кода. В текстовом поле отображается полный путь к выбранному файлу.  
  
 За счет указанных ниже настроек в диалоговом окне **Открыть файлы** отображаются только файлы с расширением WAV:  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
### <a name="to-compile-the-code"></a>Компиляция кода  
  
1.  Создайте новый проект приложения Windows на C# в Visual Studio и назовите его **WinSound**.  
  
2.  Скопируйте указанный выше код и вставьте его поверх содержимого файла `Form1.cs`.  
  
3.  Скопируйте следующий код и вставьте его в файл `Form1.Designer.cs` в метод `InitializeComponent()` имеющегося кода.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Скомпилируйте и запустите код.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Дополнительные сведения см. в разделе [Безопасность .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Подробный обзор вызова неуправляемого кода](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Маршалинг данных при вызове неуправляемого кода](../../../framework/interop/marshaling-data-with-platform-invoke.md)

