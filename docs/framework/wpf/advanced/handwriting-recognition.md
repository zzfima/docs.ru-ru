---
title: Распознавание рукописного ввода
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 417af272514ac9ce68c8faa72339f2befc2dd7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923387"
---
# <a name="handwriting-recognition"></a>Распознавание рукописного ввода
В этом разделе рассматриваются базовые понятия, связанные с распознаванием рукописного ввода на платформе WPF.  
  
## <a name="recognition-solutions"></a>Решения для распознавания рукописного ввода  
 В следующем примере показано, как распознать рукописный ввод с помощью класса [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)).  
  
> [!NOTE]
>  Этот образец требует установки в системе средств распознавания рукописного ввода.  
  
 В Visual Studio создайте проект приложения WPF с именем **InkRecognition**. Замените содержимое файла Window1.xaml следующим кодом XAML. Этот код отображает пользовательский интерфейс приложения.  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Добавьте ссылку на сборку рукописного ввода Microsoft, Microsoft.Ink.dll, которую можно найти в каталоге \Program Files\Common Files\Microsoft Shared\Ink. Замените содержимое файла кода программной части следующим кодом.  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
