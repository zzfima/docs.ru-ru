---
title: -preferreduilang (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211755"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="592b2-102">-preferreduilang (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="592b2-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="592b2-103">С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="592b2-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="592b2-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="592b2-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="592b2-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="592b2-106">[Имя языка](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx), который будет использоваться для вывода компилятора.</span><span class="sxs-lookup"><span data-stu-id="592b2-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="592b2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="592b2-107">Remarks</span></span>  
 <span data-ttu-id="592b2-108">Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки.</span><span class="sxs-lookup"><span data-stu-id="592b2-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="592b2-109">Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="592b2-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="592b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="592b2-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592b2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="592b2-111">See Also</span></span>  
 [<span data-ttu-id="592b2-112">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="592b2-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
