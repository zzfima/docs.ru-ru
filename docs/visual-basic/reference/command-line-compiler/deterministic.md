---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 9b611a72656bdd570eccec8a0585bf5ce6fa55f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716794"
---
# <a name="-deterministic"></a><span data-ttu-id="fde1b-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="fde1b-102">-deterministic</span></span>

<span data-ttu-id="fde1b-103">Указывает компилятору на необходимость создания сборки, чьи побайтовые выходные данные идентичны в разных компиляциях, если входные данные идентичны.</span><span class="sxs-lookup"><span data-stu-id="fde1b-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="fde1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fde1b-104">Syntax</span></span>

```console
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="fde1b-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="fde1b-105">Remarks</span></span>

<span data-ttu-id="fde1b-106">По умолчанию выходные данные компилятора из заданного набора входных данных являются уникальными, поскольку компилятор добавляет метку времени и идентификатор GUID, который создается из случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="fde1b-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="fde1b-107">Вы можете использовать параметр `-deterministic` для создания *детерминированной сборки*, двоичное содержимое которой идентично в разных компиляциях при условии, что входные данные не изменяются.</span><span class="sxs-lookup"><span data-stu-id="fde1b-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="fde1b-108">Компилятор учитывает идентичность следующих входных данных:</span><span class="sxs-lookup"><span data-stu-id="fde1b-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="fde1b-109">Последовательность параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="fde1b-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="fde1b-110">Содержимое RSP-файла ответов в компиляторе.</span><span class="sxs-lookup"><span data-stu-id="fde1b-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="fde1b-111">Точная версия компилятора и его связанные сборки.</span><span class="sxs-lookup"><span data-stu-id="fde1b-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="fde1b-112">Текущий путь к каталогу.</span><span class="sxs-lookup"><span data-stu-id="fde1b-112">The current directory path.</span></span>
- <span data-ttu-id="fde1b-113">Двоичное содержимое всех файлов, явным образом переданных компилятору прямо или косвенно, в том числе:</span><span class="sxs-lookup"><span data-stu-id="fde1b-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="fde1b-114">Исходные файлы</span><span class="sxs-lookup"><span data-stu-id="fde1b-114">Source files</span></span>
  - <span data-ttu-id="fde1b-115">Связанные сборки</span><span class="sxs-lookup"><span data-stu-id="fde1b-115">Referenced assemblies</span></span>
  - <span data-ttu-id="fde1b-116">Связанные модули</span><span class="sxs-lookup"><span data-stu-id="fde1b-116">Referenced modules</span></span>
  - <span data-ttu-id="fde1b-117">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="fde1b-117">Resources</span></span>
  - <span data-ttu-id="fde1b-118">Файл ключа строгого имени</span><span class="sxs-lookup"><span data-stu-id="fde1b-118">The strong name key file</span></span>
  - <span data-ttu-id="fde1b-119">Файлы ответов @</span><span class="sxs-lookup"><span data-stu-id="fde1b-119">@ response files</span></span>
  - <span data-ttu-id="fde1b-120">Анализаторы</span><span class="sxs-lookup"><span data-stu-id="fde1b-120">Analyzers</span></span>
  - <span data-ttu-id="fde1b-121">Наборы правил</span><span class="sxs-lookup"><span data-stu-id="fde1b-121">Rulesets</span></span>
  - <span data-ttu-id="fde1b-122">Дополнительные файлы, которые могут использоваться анализаторами</span><span class="sxs-lookup"><span data-stu-id="fde1b-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="fde1b-123">Текущий язык и региональные параметры (для языка сообщений о диагностике и исключениях).</span><span class="sxs-lookup"><span data-stu-id="fde1b-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="fde1b-124">Кодировка по умолчанию (или текущая кодовая страница), если кодировка не указана.</span><span class="sxs-lookup"><span data-stu-id="fde1b-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="fde1b-125">Наличие, отсутствие и содержимое файлов на пути поиска компилятора (задается, например, с помощью `-lib` или `-recurse`).</span><span class="sxs-lookup"><span data-stu-id="fde1b-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `-lib` or `-recurse`).</span></span>
- <span data-ttu-id="fde1b-126">Платформа среды CLR, в которой выполняется компилятор.</span><span class="sxs-lookup"><span data-stu-id="fde1b-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="fde1b-127">Значение `%LIBPATH%`, которое может повлиять на загрузку зависимостей анализатора.</span><span class="sxs-lookup"><span data-stu-id="fde1b-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="fde1b-128">Если источники общедоступны, детерминированную компиляцию можно использовать, чтобы установить, компилируются ли двоичные данные из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="fde1b-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="fde1b-129">Ее также можно использовать в системе непрерывной сборки, чтобы определить необходимость выполнения шагов сборки, зависящих от изменений в двоичном файле.</span><span class="sxs-lookup"><span data-stu-id="fde1b-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="fde1b-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="fde1b-130">See also</span></span>

- [<span data-ttu-id="fde1b-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="fde1b-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fde1b-132">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="fde1b-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
