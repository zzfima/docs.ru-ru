---
title: Руководство по программированию на C#. Вызов неуправляемого кода для воспроизведения WAV-файла
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 3ea90f0739ad45c31e4f25836c9de8e708dff2cc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75700826"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a>Руководство по программированию на C#. Вызов неуправляемого кода для воспроизведения WAV-файла

В следующем примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в ОС Windows.

## <a name="example"></a>Пример

В этом примере <xref:System.Runtime.InteropServices.DllImportAttribute> используется для импорта точки входа метода `winmm.dll` файла `PlaySound` как `Form1 PlaySound()`. Пример включает простую форму Windows с кнопкой. При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, позволяющее выбрать файл для воспроизведения. Выбранный WAV-файл воспроизводится с помощью метода `PlaySound()` из метода библиотеки *winmm.dll*. Дополнительные сведения об этом методе см. в разделе [Использование функции PlaySound со звуковыми WAV-файлами](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files). Найдите и выберите файл с расширением WAV и нажмите кнопку **Открыть**, чтобы воспроизвести этот WAV-файл, используя вызов неуправляемого кода. В текстовом поле отображается полный путь к выбранному файлу.

За счет указанных ниже настроек в диалоговом окне **Открыть файлы** отображаются только файлы с расширением WAV:

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a>Компиляция кода

1. Создайте проект приложения Windows Forms на C# в Visual Studio и назовите его **WinSound**.

2. Скопируйте указанный выше код и вставьте его поверх содержимого файла *Form1.cs*.

3. Скопируйте следующий код и вставьте его в файл *Form1.Designer.cs* в метод `InitializeComponent()` после существующего кода.

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. Скомпилируйте и запустите код.

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Общие сведения о взаимодействии](interoperability-overview.md)
- [Подробный обзор вызова неуправляемого кода](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Маршалинг данных при вызове неуправляемого кода](../../../framework/interop/marshaling-data-with-platform-invoke.md)
