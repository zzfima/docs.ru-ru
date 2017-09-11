---
title: "Предварительная спецификация языка C# 6.0"
ms.date: 2017-07-01
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: reference
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, specification
- what's new [C#], language specification
- Visual C#, C# language specification
- language specification [C#]
ms.assetid: e5d5a5cc-636b-4bff-b9c8-a8edc6207c22
caps.latest.revision: 46
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
ms.sourcegitcommit: dbc7f6ad4e6ddd30b3c808840420335a0c0155ad
ms.openlocfilehash: 904b0f5bf99ed133eb505f65faaa63ca99053f5a
ms.contentlocale: ru-ru
ms.lasthandoff: 08/23/2017

---
# <a name="c-60-draft-language-specification"></a><span data-ttu-id="bd5a4-102">Предварительная спецификация языка C# 6.0</span><span class="sxs-lookup"><span data-stu-id="bd5a4-102">C# 6.0 draft Language Specification</span></span>
<span data-ttu-id="bd5a4-103">Спецификация языка C# является нормативным источником синтаксиса и использования C#.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-103">The C# Language Specification is the definitive source for C# syntax and usage.</span></span> <span data-ttu-id="bd5a4-104">Она содержит подробные сведения обо всех аспектах языка, включая многие моменты, которые не раскрываются в документации Visual C#.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-104">This specification contains detailed information about all aspects of the language, including many points that the documentation for Visual C# doesn't cover.</span></span>

<span data-ttu-id="bd5a4-105">Версию 5.0 этой спецификации можно скачать в [Центре загрузки Майкрософт](http://www.microsoft.com/download/details.aspx?id=7029).</span><span class="sxs-lookup"><span data-stu-id="bd5a4-105">You can download version 5.0 of this specification from the [Microsoft Download Center](http://www.microsoft.com/download/details.aspx?id=7029).</span></span> <span data-ttu-id="bd5a4-106">Если вы уже установили Visual Studio 2015, эту спецификацию можно также найти на компьютере в папке Program Files (x86)/Microsoft Visual Studio 14.0/VC#/Specifications/1033.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-106">If you've installed Visual Studio 2015, you can also find the specification on your computer in the Program Files (x86)/Microsoft Visual Studio 14.0/VC#/Specifications/1033 folder.</span></span> <span data-ttu-id="bd5a4-107">Если у вас установлена другая версия Visual Studio или среда Visual Studio установлена на языке, отличном от английского, измените путь соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-107">If you have another version of Visual Studio installed or if you installed Visual Studio in a language other than English, change the path as appropriate.</span></span>

<span data-ttu-id="bd5a4-108">Версия спецификации 6.0 не была утверждена как стандартная.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-108">Version 6.0 of the specification has not been approved as a standard.</span></span> <span data-ttu-id="bd5a4-109">Этот сайт содержит [*предварительную* спецификацию C# 6.0](../../../../_csharplang/spec/lexical-structure.md).</span><span class="sxs-lookup"><span data-stu-id="bd5a4-109">This site contains the [*draft* C# 6.0 specification](../../../../_csharplang/spec/lexical-structure.md).</span></span> <span data-ttu-id="bd5a4-110">Она создана на основе файлов Markdown, содержащихся в [GitHub-репозитории dotnet/csharplang](https://github.com/dotnet/csharplang/blob/master/spec/README.md).</span><span class="sxs-lookup"><span data-stu-id="bd5a4-110">It is built from the markdown files contained in [the dotnet/csharplang GitHub repository](https://github.com/dotnet/csharplang/blob/master/spec/README.md).</span></span>

<span data-ttu-id="bd5a4-111">Найденные в предварительной спецификации проблемы следует публиковать в репозитории [dotnet/csharplang](https://github.com/dotnet/csharplang/issues).</span><span class="sxs-lookup"><span data-stu-id="bd5a4-111">Issues on the draft specification should be created in the [dotnet/csharplang](https://github.com/dotnet/csharplang/issues) repository.</span></span> <span data-ttu-id="bd5a4-112">Если же вам интересно исправить какие-то из найденных вами ошибок, вы можете отправить [запрос на вытягивание](https://github.com/dotnet/csharplang/pulls) в тот же репозиторий.</span><span class="sxs-lookup"><span data-stu-id="bd5a4-112">Or, if you are interested in fixing any errors you find, you may submit a [Pull Request](https://github.com/dotnet/csharplang/pulls) to the same repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd5a4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bd5a4-113">See Also</span></span>  
 [<span data-ttu-id="bd5a4-114">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="bd5a4-114">C# Reference</span></span>](../../language-reference/index.md)  
 [<span data-ttu-id="bd5a4-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="bd5a4-115">C# Programming Guide</span></span>](../../programming-guide/index.md)

>[!div class="step-by-step"]
[<span data-ttu-id="bd5a4-116">Вперед</span><span class="sxs-lookup"><span data-stu-id="bd5a4-116">Next</span></span>](../../../../_csharplang/spec/lexical-structure.md)

