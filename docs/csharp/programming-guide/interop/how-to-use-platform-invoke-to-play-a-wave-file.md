---
title: "Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2aacad0e8004e60471a59ebef695ddae5f7a2a7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="79e9d-102">Практическое руководство. Использование вызова неуправляемого кода для воспроизведения звукового файла (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="79e9d-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="79e9d-103">В следующем примере кода C# показано, как использовать службы вызова неуправляемого кода для воспроизведения звуковых WAV-файлов в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="79e9d-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e9d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="79e9d-104">Example</span></span>  
 <span data-ttu-id="79e9d-105">В этом примере `DllImport` используется для импорта точки входа метода `PlaySound` файла `winmm.dll` как `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="79e9d-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="79e9d-106">Пример включает простую форму Windows с кнопкой.</span><span class="sxs-lookup"><span data-stu-id="79e9d-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="79e9d-107">При нажатии кнопки открывается стандартное диалоговое окно Windows <xref:System.Windows.Forms.OpenFileDialog>, позволяющее выбрать файл для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="79e9d-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="79e9d-108">Выбранный WAV-файл воспроизводится с помощью метода `PlaySound()` из метода сборки winmm.dll.</span><span class="sxs-lookup"><span data-stu-id="79e9d-108">When a wave file is selected, it is played by using the `PlaySound()` method of the winmm.DLL assembly method.</span></span> <span data-ttu-id="79e9d-109">Дополнительные сведения о методе `PlaySound` winmm.dll см. в статье [Использование функции PlaySound со звуковыми WAV-файлами](http://go.microsoft.com/fwlink/?LinkId=148553).</span><span class="sxs-lookup"><span data-stu-id="79e9d-109">For more information about winmm.dll's `PlaySound` method, see [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).</span></span> <span data-ttu-id="79e9d-110">Найдите и выберите файл с расширением WAV и нажмите кнопку **Открыть**, чтобы воспроизвести этот WAV-файл, используя вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="79e9d-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="79e9d-111">В текстовом поле отображается полный путь к выбранному файлу.</span><span class="sxs-lookup"><span data-stu-id="79e9d-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="79e9d-112">За счет указанных ниже настроек в диалоговом окне **Открыть файлы** отображаются только файлы с расширением WAV:</span><span class="sxs-lookup"><span data-stu-id="79e9d-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79e9d-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="79e9d-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="79e9d-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="79e9d-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="79e9d-115">Создайте новый проект приложения Windows на C# в Visual Studio и назовите его **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="79e9d-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="79e9d-116">Скопируйте указанный выше код и вставьте его поверх содержимого файла `Form1.cs`.</span><span class="sxs-lookup"><span data-stu-id="79e9d-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="79e9d-117">Скопируйте следующий код и вставьте его в файл `Form1.Designer.cs` в метод `InitializeComponent()` имеющегося кода.</span><span class="sxs-lookup"><span data-stu-id="79e9d-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="79e9d-118">Скомпилируйте и запустите код.</span><span class="sxs-lookup"><span data-stu-id="79e9d-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="79e9d-119">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79e9d-119">.NET Framework Security</span></span>  
 <span data-ttu-id="79e9d-120">Дополнительные сведения см. в разделе [Безопасность .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="79e9d-120">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e9d-121">См. также</span><span class="sxs-lookup"><span data-stu-id="79e9d-121">See Also</span></span>  
 [<span data-ttu-id="79e9d-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="79e9d-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79e9d-123">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="79e9d-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="79e9d-124">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="79e9d-124">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="79e9d-125">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="79e9d-125">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="79e9d-126">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="79e9d-126">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
