---
title: "-preferreduilang (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4fcf075dd951d733d294a62de98365c77b16a51d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="06950-102">-preferreduilang (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="06950-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="06950-103">С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="06950-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06950-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06950-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="06950-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="06950-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="06950-106">[Имя языка](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx), который будет использоваться для вывода компилятора.</span><span class="sxs-lookup"><span data-stu-id="06950-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06950-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="06950-107">Remarks</span></span>  
 <span data-ttu-id="06950-108">Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки.</span><span class="sxs-lookup"><span data-stu-id="06950-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="06950-109">Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="06950-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="06950-110">Требования</span><span class="sxs-lookup"><span data-stu-id="06950-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06950-111">См. также</span><span class="sxs-lookup"><span data-stu-id="06950-111">See Also</span></span>  
 [<span data-ttu-id="06950-112">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="06950-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
