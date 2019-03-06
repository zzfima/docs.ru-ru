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
ms.openlocfilehash: 08cd9e0a167d1bef9bbe6437b22985082c80e5f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365806"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="0bcab-102">Распознавание рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="0bcab-102">Handwriting Recognition</span></span>
<span data-ttu-id="0bcab-103">В этом разделе рассматриваются базовые понятия, связанные с распознаванием рукописного ввода на платформе WPF.</span><span class="sxs-lookup"><span data-stu-id="0bcab-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="0bcab-104">Решения для распознавания рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="0bcab-104">Recognition Solutions</span></span>  
 <span data-ttu-id="0bcab-105">В следующем примере показано, как распознать рукописный ввод с помощью класса [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0bcab-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bcab-106">Этот образец требует установки в системе средств распознавания рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="0bcab-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="0bcab-107">В Visual Studio создайте проект приложения WPF с именем **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="0bcab-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="0bcab-108">Замените содержимое файла Window1.xaml следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="0bcab-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="0bcab-109">Этот код отображает пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="0bcab-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="0bcab-110">Добавьте ссылку на сборку рукописного ввода Microsoft, Microsoft.Ink.dll, которую можно найти в каталоге \Program Files\Common Files\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="0bcab-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="0bcab-111">Замените содержимое файла кода программной части следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="0bcab-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0bcab-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0bcab-112">See also</span></span>
- <span data-ttu-id="0bcab-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0bcab-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span></span>
