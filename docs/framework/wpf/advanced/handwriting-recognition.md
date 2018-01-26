---
title: "Распознавание рукописного ввода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 384f21587c29e6afe82964fc28432f5a6be92b05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="handwriting-recognition"></a>Распознавание рукописного ввода
В этом разделе рассматриваются базовые понятия, связанные с распознаванием рукописного ввода на платформе WPF.  
  
## <a name="recognition-solutions"></a>Решения для распознавания рукописного ввода  
 В следующем примере показано, как распознать рукописный ввод с помощью класса [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).  
  
> [!NOTE]
>  Этот образец требует установки в системе средств распознавания рукописного ввода.  
  
 В Visual Studio создайте проект приложения WPF с именем **InkRecognition**. Замените содержимое файла Window1.xaml следующим кодом XAML. Этот код отображает пользовательский интерфейс приложения.  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Добавьте ссылку на сборку рукописного ввода Microsoft, Microsoft.Ink.dll, которую можно найти в каталоге \Program Files\Common Files\Microsoft Shared\Ink. Замените содержимое файла кода программной части следующим кодом.  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)
