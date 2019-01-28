---
title: Как выполнить Руководство по программированию на C#. Использование вызова неуправляемого кода для воспроизведения звукового файла
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 94c90ed264c40c99b0c139948578c85e8c9855d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696351"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование вызова неуправляемого кода для воспроизведения звукового файла
В следующем примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в операционной системе Windows.  
  
## <a name="example"></a>Пример  
 В этом примере `DllImport` используется для импорта точки входа метода `PlaySound` файла `winmm.dll` как `Form1 PlaySound()`. Пример включает простую форму Windows с кнопкой. При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, позволяющее выбрать файл для воспроизведения. Выбранный WAV-файл воспроизводится с помощью метода `PlaySound()` из библиотеки `winmm.dll`. Дополнительные сведения об этом методе см. в разделе [Использование функции PlaySound со звуковыми WAV-файлами](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files). Найдите и выберите файл с расширением WAV и нажмите кнопку **Открыть**, чтобы воспроизвести этот WAV-файл, используя вызов неуправляемого кода. В текстовом поле отображается полный путь к выбранному файлу.  
  
 За счет указанных ниже настроек в диалоговом окне **Открыть файлы** отображаются только файлы с расширением WAV:  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
### <a name="to-compile-the-code"></a>Компиляция кода  
  
1.  Создайте новый проект приложения Windows на C# в Visual Studio и назовите его **WinSound**.  
  
2.  Скопируйте указанный выше код и вставьте его поверх содержимого файла `Form1.cs`.  
  
3.  Скопируйте следующий код и вставьте его в файл `Form1.Designer.cs` в метод `InitializeComponent()` имеющегося кода.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Скомпилируйте и запустите код.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Дополнительные сведения см. в разделе [Безопасность в .NET](../../../standard/security/index.md).  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)
- [Подробный обзор вызова неуправляемого кода](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Маршалинг данных при вызове неуправляемого кода](../../../framework/interop/marshaling-data-with-platform-invoke.md)
