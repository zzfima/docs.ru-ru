---
title: "-utf8output (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3716445cb779e98f777a1677ff67e1ba603c5fa2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="70f4b-102">-utf8output (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="70f4b-102">-utf8output (C# Compiler Options)</span></span>
<span data-ttu-id="70f4b-103">Параметр **-utf8output** отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="70f4b-103">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70f4b-104">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="70f4b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="70f4b-105">Remarks</span></span>  
 <span data-ttu-id="70f4b-106">В некоторых конфигурациях для различных языков выходные данные компилятора некорректно отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="70f4b-106">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="70f4b-107">В таких конфигурациях следует использовать параметр **-utf8output** для перенаправления выходных данных компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="70f4b-107">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="70f4b-108">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="70f4b-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f4b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="70f4b-109">See Also</span></span>  
 [<span data-ttu-id="70f4b-110">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="70f4b-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
