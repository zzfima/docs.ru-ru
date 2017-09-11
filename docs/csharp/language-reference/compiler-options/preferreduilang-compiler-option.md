---
title: "-preferreduilang (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /preferreduilang
dev_langs:
- CSharp
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b94c2794642ad93a78eaafdeb655310e4ecb2d25
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="preferreduilang-c-compiler-options"></a><span data-ttu-id="4c5e5-102">/preferreduilang (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="4c5e5-102">/preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="4c5e5-103">С помощью параметра компилятора `/preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="4c5e5-103">By using the `/preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c5e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c5e5-104">Syntax</span></span>  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="4c5e5-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4c5e5-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="4c5e5-106">[Имя языка](http://go.microsoft.com/fwlink/p/?LinkId=236992), который будет использоваться для вывода компилятора.</span><span class="sxs-lookup"><span data-stu-id="4c5e5-106">The [language name](http://go.microsoft.com/fwlink/p/?LinkId=236992) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c5e5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4c5e5-107">Remarks</span></span>  
 <span data-ttu-id="4c5e5-108">Можно использовать параметр компилятора `/preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки.</span><span class="sxs-lookup"><span data-stu-id="4c5e5-108">You can use the `/preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="4c5e5-109">Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="4c5e5-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="4c5e5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4c5e5-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5e5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4c5e5-111">See Also</span></span>  
 [<span data-ttu-id="4c5e5-112">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="4c5e5-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

