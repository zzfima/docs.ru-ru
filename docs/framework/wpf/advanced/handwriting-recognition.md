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
ms.openlocfilehash: f8a202d4698c968a91a3d930138290cedfe3a83b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="handwriting-recognition"></a><span data-ttu-id="b5989-102">Распознавание рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="b5989-102">Handwriting Recognition</span></span>
<span data-ttu-id="b5989-103">В этом разделе рассматриваются базовые понятия, связанные с распознаванием рукописного ввода на платформе WPF.</span><span class="sxs-lookup"><span data-stu-id="b5989-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="b5989-104">Решения для распознавания рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="b5989-104">Recognition Solutions</span></span>  
 <span data-ttu-id="b5989-105">В следующем примере показано, как распознать рукописный ввод с помощью класса [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).</span><span class="sxs-lookup"><span data-stu-id="b5989-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5989-106">Этот образец требует установки в системе средств распознавания рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="b5989-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="b5989-107">В Visual Studio создайте проект приложения WPF с именем **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="b5989-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="b5989-108">Замените содержимое файла Window1.xaml следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="b5989-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="b5989-109">Этот код отображает пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="b5989-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b5989-110">Добавьте ссылку на сборку рукописного ввода Microsoft, Microsoft.Ink.dll, которую можно найти в каталоге \Program Files\Common Files\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="b5989-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="b5989-111">Замените содержимое файла кода программной части следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="b5989-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b5989-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b5989-112">See Also</span></span>  
 <span data-ttu-id="b5989-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b5989-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
