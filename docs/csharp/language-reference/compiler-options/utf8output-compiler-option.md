---
title: -utf8output (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
ms.openlocfilehash: 32c239f7563101cb1dddedbf868d298806353492
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476265"
---
# <a name="-utf8output-c-compiler-options"></a><span data-ttu-id="65bcf-102">-utf8output (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="65bcf-102">-utf8output (C# Compiler Options)</span></span>
<span data-ttu-id="65bcf-103">Параметр **-utf8output** отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="65bcf-103">The **-utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65bcf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65bcf-104">Syntax</span></span>  
  
```console  
-utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="65bcf-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="65bcf-105">Remarks</span></span>  
 <span data-ttu-id="65bcf-106">В некоторых конфигурациях для различных языков выходные данные компилятора некорректно отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="65bcf-106">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="65bcf-107">В таких конфигурациях следует использовать параметр **-utf8output** для перенаправления выходных данных компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="65bcf-107">In these configurations, use **-utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="65bcf-108">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="65bcf-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bcf-109">См. также</span><span class="sxs-lookup"><span data-stu-id="65bcf-109">See Also</span></span>  

- [<span data-ttu-id="65bcf-110">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="65bcf-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
