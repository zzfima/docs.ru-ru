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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602557"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="65a38-102">-preferreduilang (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="65a38-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="65a38-103">С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="65a38-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65a38-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="65a38-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="65a38-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="65a38-106">[Имя языка](/windows/desktop/Intl/language-names), который будет использоваться для вывода компилятора.</span><span class="sxs-lookup"><span data-stu-id="65a38-106">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65a38-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="65a38-107">Remarks</span></span>  
 <span data-ttu-id="65a38-108">Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки.</span><span class="sxs-lookup"><span data-stu-id="65a38-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="65a38-109">Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="65a38-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="65a38-110">Требования</span><span class="sxs-lookup"><span data-stu-id="65a38-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a38-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65a38-111">See also</span></span>

- [<span data-ttu-id="65a38-112">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="65a38-112">C# Compiler Options</span></span>](./index.md)
