---
title: -Детерминированные
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="430ca-102">-Детерминированные</span><span class="sxs-lookup"><span data-stu-id="430ca-102">-deterministic</span></span>

<span data-ttu-id="430ca-103">Указывает компилятору создать сборку, выходные данные которого байт для байтом идентична для всех компиляциях для идентичных входных данных.</span><span class="sxs-lookup"><span data-stu-id="430ca-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="430ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="430ca-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="430ca-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="430ca-105">Remarks</span></span>

<span data-ttu-id="430ca-106">По умолчанию выходные данные компилятора из заданного набора входных данных является уникальным, поскольку компилятор добавляет отметку времени и идентификатор GUID, который создается на основе случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="430ca-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="430ca-107">Вы используете `-deterministic` параметр для создания *детерминированным сборки*, одно двоичное содержимое которого идентичен через компиляций при условии, что входные данные не изменяется.</span><span class="sxs-lookup"><span data-stu-id="430ca-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="430ca-108">Компилятор считает, что следующие входные данные с целью детерминизм:</span><span class="sxs-lookup"><span data-stu-id="430ca-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="430ca-109">Последовательность параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="430ca-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="430ca-110">Содержимое компилятора RSP-файл ответа.</span><span class="sxs-lookup"><span data-stu-id="430ca-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="430ca-111">Точные версии компилятора и его связанные сборки.</span><span class="sxs-lookup"><span data-stu-id="430ca-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="430ca-112">Текущий путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="430ca-112">The current directory path.</span></span>
- <span data-ttu-id="430ca-113">Двоичное содержимое всех файлов явным образом передать компилятору прямо или косвенно, включая:</span><span class="sxs-lookup"><span data-stu-id="430ca-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="430ca-114">Исходные файлы</span><span class="sxs-lookup"><span data-stu-id="430ca-114">Source files</span></span>
    - <span data-ttu-id="430ca-115">связанные сборки</span><span class="sxs-lookup"><span data-stu-id="430ca-115">Referenced assemblies</span></span>
    - <span data-ttu-id="430ca-116">Модули, на которые имеются ссылки</span><span class="sxs-lookup"><span data-stu-id="430ca-116">Referenced modules</span></span>
    - <span data-ttu-id="430ca-117">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="430ca-117">Resources</span></span>
    - <span data-ttu-id="430ca-118">Файл ключей строгого имени</span><span class="sxs-lookup"><span data-stu-id="430ca-118">The strong name key file</span></span>
    - <span data-ttu-id="430ca-119">@ файлы ответа</span><span class="sxs-lookup"><span data-stu-id="430ca-119">@ response files</span></span>
    - <span data-ttu-id="430ca-120">Анализаторы</span><span class="sxs-lookup"><span data-stu-id="430ca-120">Analyzers</span></span>
    - <span data-ttu-id="430ca-121">Наборы правил</span><span class="sxs-lookup"><span data-stu-id="430ca-121">Rulesets</span></span>
    - <span data-ttu-id="430ca-122">Дополнительные файлы, которые могут использоваться анализаторами</span><span class="sxs-lookup"><span data-stu-id="430ca-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="430ca-123">Текущий язык и региональные параметры (для языка, в какие диагностики и исключения создаются сообщения).</span><span class="sxs-lookup"><span data-stu-id="430ca-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="430ca-124">Кодировка по умолчанию (или текущую кодовую страницу) Если не указана кодировка.</span><span class="sxs-lookup"><span data-stu-id="430ca-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="430ca-125">Существование, отличных от существования и содержимое файлов на пути поиска компилятора (заданные, например, `/lib` или `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="430ca-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="430ca-126">Платформа среды CLR, в которой выполняется компилятором.</span><span class="sxs-lookup"><span data-stu-id="430ca-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="430ca-127">Значение `%LIBPATH%`, которое может повлиять на загрузку зависимостей анализатора.</span><span class="sxs-lookup"><span data-stu-id="430ca-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="430ca-128">Если источники публично доступны, детерминированную компиляцию можно использовать для установления, компилируется ли двоичные данные из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="430ca-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="430ca-129">Его также можно использовать в непрерывном режиме построения системе для определения того, необходимо выполнить шаги построения, зависящих от изменений в двоичном файле.</span><span class="sxs-lookup"><span data-stu-id="430ca-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="430ca-130">См. также</span><span class="sxs-lookup"><span data-stu-id="430ca-130">See Also</span></span>
[<span data-ttu-id="430ca-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="430ca-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="430ca-132">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="430ca-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
