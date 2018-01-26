---
title: "Практическое руководство. Асинхронная загрузка звука в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05c993763bdc436b5912515e0aa83e3a29f7bb83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a>Практическое руководство. Асинхронная загрузка звука в Windows Forms
В примере кода ниже производится асинхронная загрузка звука по URL-адресу, после чего он воспроизводится в новом потоке.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms;  
  
-   замена имени файла `"http://www.tailspintoys.com/sounds/stop.wav"` на допустимое имя файла.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Операции с файлами должны быть включены в соответствующие блоки обработки исключений.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Недопустимое имя пути (например, путь содержит недопустимые символы или состоит только из пробелов (класс <xref:System.ArgumentException>)).  
  
-   Путь доступен только для чтения (класс <xref:System.IO.IOException>).  
  
-   Имя пути — `Nothing` (класс <xref:System.ArgumentNullException>).  
  
-   Указано слишком длинное имя пути (класс <xref:System.IO.PathTooLongException>).  
  
-   Недопустимый путь (класс <xref:System.IO.DirectoryNotFoundException>).  
  
-   Путь содержит только двоеточие (":") (класс <xref:System.NotSupportedException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 По имени файла не всегда можно с уверенностью судить о его содержимом. Например, файл с именем `Form1.vb` может вовсе не быть исходным файлом Visual Basic. Следует проверять все входные данные перед использованием их в приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [Практическое руководство. Воспроизведение звука в Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
