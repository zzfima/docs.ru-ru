---
title: Многофайловые сборки
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 862fc7012c2c5c84a163d6716dfeb4b97f00cbcd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634181"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="4c452-102">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="4c452-102">Multifile Assemblies</span></span>

<span data-ttu-id="4c452-103">Многофайловые сборки можно создавать с помощью компиляторов командной строки или в Visual Studio, используя Visual C++.</span><span class="sxs-lookup"><span data-stu-id="4c452-103">You can create multifile assemblies using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="4c452-104">Один из файлов сборки обязательно должен содержать ее манифест.</span><span class="sxs-lookup"><span data-stu-id="4c452-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="4c452-105">Кроме того, сборка, запускающая приложение, должна содержать точку входа, такую как метод Main или WinMain.</span><span class="sxs-lookup"><span data-stu-id="4c452-105">An assembly that starts an application must also contain an entry point, such as a Main or WinMain method.</span></span>

<span data-ttu-id="4c452-106">Например, предположим, что есть приложение, содержащее два модуля кода — Client.cs и Stringer.cs.</span><span class="sxs-lookup"><span data-stu-id="4c452-106">For example, suppose you have an application that contains two code modules, Client.cs and Stringer.cs.</span></span> <span data-ttu-id="4c452-107">Модуль Stringer.cs создает пространство имен `myStringer`, на которое ссылается код в модуле Client.cs.</span><span class="sxs-lookup"><span data-stu-id="4c452-107">Stringer.cs creates the `myStringer` namespace that is referenced by the code in Client.cs.</span></span> <span data-ttu-id="4c452-108">Модуль Client.cs содержит метод `Main`, который является точкой входа приложения.</span><span class="sxs-lookup"><span data-stu-id="4c452-108">Client.cs contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="4c452-109">В этом примере выполняется компиляция двух модулей кода, затем создается третий файл, содержащий манифест сборки, который и запускает приложение.</span><span class="sxs-lookup"><span data-stu-id="4c452-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="4c452-110">Манифест сборки ссылается и на модуль`Client`, и на `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="4c452-110">The assembly manifest references both the `Client` and `Stringer` modules.</span></span>

> [!NOTE]
> <span data-ttu-id="4c452-111">Многофайловые сборки могут иметь только одну точку входа, даже если сборка содержит несколько модулей кода.</span><span class="sxs-lookup"><span data-stu-id="4c452-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="4c452-112">Существует несколько причин, по которым может понадобиться создать многофайловую сборку.</span><span class="sxs-lookup"><span data-stu-id="4c452-112">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="4c452-113">Для объединения модулей, написанных на различных языках.</span><span class="sxs-lookup"><span data-stu-id="4c452-113">To combine modules written in different languages.</span></span> <span data-ttu-id="4c452-114">Это наиболее частая причина создания многофайловой сборки.</span><span class="sxs-lookup"><span data-stu-id="4c452-114">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="4c452-115">Для оптимизации загрузки приложения путем выделения редко используемых типов в модуль, загружаемый только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="4c452-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c452-116">При создании приложений, загружаемых в браузере Microsoft Internet Explorer с помощью тега `<object>`, важно создавать именно многофайловые сборки.</span><span class="sxs-lookup"><span data-stu-id="4c452-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="4c452-117">Согласно этому сценарию создается отдельный от модулей кода файл, который содержит только манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="4c452-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="4c452-118">Обозреватель Internet Explorer в первую очередь загружает манифест, а затем создает рабочие потоки для загрузки любых требуемых дополнительных модулей или сборок.</span><span class="sxs-lookup"><span data-stu-id="4c452-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="4c452-119">При загрузке файла, содержащего манифест сборки, обозреватель Internet Explorer не реагирует на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c452-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="4c452-120">Чем меньше размер файла, содержащего манифест сборки, тем меньше времени обозреватель Internet Explorer будет оставаться в таком состоянии.</span><span class="sxs-lookup"><span data-stu-id="4c452-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="4c452-121">Для объединения модулей кода, созданных несколькими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="4c452-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="4c452-122">Несмотря на то что каждый разработчик может скомпилировать модуль кода в сборку, это может привести к принудительному экспорту некоторых типов, которые бы не экспортировались, если бы все модули были помещены в многофайловую сборку.</span><span class="sxs-lookup"><span data-stu-id="4c452-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="4c452-123">Сразу же после создания сборки можно подписать файл, содержащий манифест сборки (и, следовательно, подписать саму сборку), или же задать для файла (и для сборки) строгое имя и поместить его в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="4c452-123">Once you create the assembly, you can sign the file that contains the assembly manifest (and hence the assembly), or you can give the file (and the assembly) a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c452-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4c452-124">See also</span></span>

- [<span data-ttu-id="4c452-125">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="4c452-125">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="4c452-126">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="4c452-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
