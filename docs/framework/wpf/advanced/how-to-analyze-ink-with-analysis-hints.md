---
title: Практическое руководство. Анализ данных рукописного ввода с помощью подсказок анализа
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: a4c38ddf52e9054fe9126df4b7e172548617b90d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375484"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="a430d-102">Практическое руководство. Анализ данных рукописного ввода с помощью подсказок анализа</span><span class="sxs-lookup"><span data-stu-id="a430d-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="a430d-103">[System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) предоставляет подсказку для [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) к которому он присоединен.</span><span class="sxs-lookup"><span data-stu-id="a430d-103">An [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="a430d-104">Указание применяется к области, заданной [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) свойство [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) и предоставляет дополнительный контекст к анализатору рукописного ввода повышения точности распознавания.</span><span class="sxs-lookup"><span data-stu-id="a430d-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="a430d-105">[System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) применяет эти сведения при анализ рукописного ввода полученных в пределах области подсказок.</span><span class="sxs-lookup"><span data-stu-id="a430d-105">The [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a430d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a430d-106">Example</span></span>  
 <span data-ttu-id="a430d-107">Следующий пример — это приложение, в которой используется несколько [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) объектов в форме, которая принимает входные данные рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="a430d-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="a430d-108">Приложение использует [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) свойство, чтобы предоставить сведения о контексте для каждой записи в форме.</span><span class="sxs-lookup"><span data-stu-id="a430d-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="a430d-109">Приложение использует фоновый анализ для анализа рукописного ввода и очищает формы все рукописные данные через пять секунд после пользователь останавливает добавление рукописного ввода.</span><span class="sxs-lookup"><span data-stu-id="a430d-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
