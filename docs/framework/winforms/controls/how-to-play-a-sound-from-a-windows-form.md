---
title: Практическое руководство. Воспроизведение звука в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playing sounds [Windows Forms], Windows Forms
- sounds [Windows Forms], playing
- sounds
- My.Computer.Audio object [Windows Forms], playing sounds
- examples [Windows Forms], sounds
ms.assetid: 3d3350b7-1ebd-4e05-a738-48ca1160a19d
ms.openlocfilehash: 7d8c723fc995e8b9987681e3db343c43d3bc2682
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714714"
---
# <a name="how-to-play-a-sound-from-a-windows-form"></a><span data-ttu-id="7cad4-102">Практическое руководство. Воспроизведение звука в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cad4-102">How to: Play a Sound from a Windows Form</span></span>
<span data-ttu-id="7cad4-103">В этом примере воспроизводится звук по заданному пути во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7cad4-103">This example plays a sound at a given path at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cad4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7cad4-104">Example</span></span>  
  
```vb  
Sub PlaySimpleSound()  
    My.Computer.Audio.Play("c:\Windows\Media\chimes.wav")  
End Sub  
```  
  
```csharp  
private void playSimpleSound()  
{  
    SoundPlayer simpleSound = new SoundPlayer(@"c:\Windows\Media\chimes.wav");  
    simpleSound.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7cad4-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7cad4-105">Compiling the Code</span></span>  
 <span data-ttu-id="7cad4-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7cad4-106">This example requires:</span></span>  
  
-   <span data-ttu-id="7cad4-107">замена имени файла `"c:\Windows\Media\chimes.wav"` на допустимое имя файла.</span><span class="sxs-lookup"><span data-stu-id="7cad4-107">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
-   <span data-ttu-id="7cad4-108">(C#) Ссылку на <xref:System.Media?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7cad4-108">(C#) A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7cad4-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="7cad4-109">Robust Programming</span></span>  
 <span data-ttu-id="7cad4-110">Операции с файлами должны быть включены в соответствующие структурированные блоки обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="7cad4-110">File operations should be enclosed within appropriate structured exception handling blocks.</span></span>  
  
 <span data-ttu-id="7cad4-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="7cad4-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="7cad4-112">Недопустимое имя пути</span><span class="sxs-lookup"><span data-stu-id="7cad4-112">The path name is malformed.</span></span> <span data-ttu-id="7cad4-113">Например, оно содержит недопустимые символы или состоит из одних пробелов (класс <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="7cad4-113">For example, it contains illegal characters or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="7cad4-114">Путь доступен только для чтения (класс <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="7cad4-114">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="7cad4-115">Имя пути — `null` (класс <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="7cad4-115">The path name is `null` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="7cad4-116">Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="7cad4-116">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="7cad4-117">Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="7cad4-117">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="7cad4-118">Путь содержит только двоеточие, «:» (<xref:System.NotSupportedException> класса).</span><span class="sxs-lookup"><span data-stu-id="7cad4-118">The path is only a colon, ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7cad4-119">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7cad4-119">.NET Framework Security</span></span>  
 <span data-ttu-id="7cad4-120">По имени файла не всегда можно с уверенностью судить о его содержимом.</span><span class="sxs-lookup"><span data-stu-id="7cad4-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="7cad4-121">Например, файл с именем `Form1.vb` может вовсе не быть исходным файлом Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7cad4-121">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="7cad4-122">Следует проверять все входные данные перед использованием их в приложении.</span><span class="sxs-lookup"><span data-stu-id="7cad4-122">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cad4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7cad4-123">See also</span></span>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="7cad4-124">Практическое руководство. Загрузка звука асинхронно в форме Windows</span><span class="sxs-lookup"><span data-stu-id="7cad4-124">How to: Load a Sound Asynchronously within a Windows Form</span></span>](how-to-load-a-sound-asynchronously-within-a-windows-form.md)

