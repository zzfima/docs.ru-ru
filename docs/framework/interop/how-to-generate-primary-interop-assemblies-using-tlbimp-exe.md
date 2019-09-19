---
title: Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac60fa96b7c9ce6991f89e8c6a37ff5da4a34a50
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051781"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="2fb46-102">Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="2fb46-102">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="2fb46-103">Существует два способа создания основной сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2fb46-103">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="2fb46-104">С помощью [программы импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), предоставляемой Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="2fb46-104">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="2fb46-105">Использование [программы Tlbimp.exe](../tools/tlbimp-exe-type-library-importer.md) — это самый простой способ создания основных сборок взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2fb46-105">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="2fb46-106">Эта программа предоставляет следующие меры безопасности:</span><span class="sxs-lookup"><span data-stu-id="2fb46-106">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="2fb46-107">перед созданием сборок взаимодействия для ссылок на любые вложенные библиотеки типов проверяет наличие других зарегистрированных основных сборок взаимодействия;</span><span class="sxs-lookup"><span data-stu-id="2fb46-107">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="2fb46-108">отказывается создавать основную сборку взаимодействия, если не указан контейнер или имя файла, позволяющие присвоить строгое имя основной сборке взаимодействия;</span><span class="sxs-lookup"><span data-stu-id="2fb46-108">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="2fb46-109">отказывается создавать основную сборку взаимодействия, если пропущены ссылки на зависимые сборки;</span><span class="sxs-lookup"><span data-stu-id="2fb46-109">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="2fb46-110">отказывается создавать основную сборку взаимодействия, если вы добавили ссылки на зависимые сборки, не являющиеся основными сборками взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2fb46-110">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="2fb46-111">Создание основных сборок взаимодействия в исходном коде вручную с помощью языка, совместимого со спецификацией CLS, например C#.</span><span class="sxs-lookup"><span data-stu-id="2fb46-111">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="2fb46-112">Этот подход полезен, когда библиотека типов недоступна.</span><span class="sxs-lookup"><span data-stu-id="2fb46-112">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="2fb46-113">Для подписи сборки строгим именем необходимо иметь пару криптографических ключей.</span><span class="sxs-lookup"><span data-stu-id="2fb46-113">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="2fb46-114">Подробнее см. в разделе [Создание пары ключей](../../standard/assembly/create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="2fb46-114">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="2fb46-115">Создание основной сборки взаимодействия с помощью программы Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="2fb46-115">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="2fb46-116">В командной строке введите следующее:</span><span class="sxs-lookup"><span data-stu-id="2fb46-116">At the command prompt, type:</span></span>

    <span data-ttu-id="2fb46-117">**tlbimp** *файл_tlb* **/primary /keyfile:** *имя_файла* **/out:** *имя_сборки*</span><span class="sxs-lookup"><span data-stu-id="2fb46-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="2fb46-118">В этой команде *файл_tlb* — это файл, содержащий библиотеку типов COM, *имя_файла* — это имя контейнера или файла, содержащего пару ключей, а *имя_сборки* — это имя сборки, которую необходимо подписать строгим именем.</span><span class="sxs-lookup"><span data-stu-id="2fb46-118">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="2fb46-119">Основные сборки взаимодействия могут ссылаться только на другие основные сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="2fb46-119">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="2fb46-120">Если сборка ссылается на типы из библиотеки типов COM стороннего разработчика, то перед созданием собственной основной сборки взаимодействия необходимо получить основную сборку взаимодействия от издателя.</span><span class="sxs-lookup"><span data-stu-id="2fb46-120">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="2fb46-121">Если издателем являетесь вы, перед созданием ссылающейся основной сборки взаимодействия нужно создать основную сборку взаимодействия для зависимой библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2fb46-121">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="2fb46-122">Зависимую основную сборку взаимодействия с номером версии, отличающимся от номера версии исходной библиотеки типов, невозможно обнаружить при установке в текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="2fb46-122">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="2fb46-123">Необходимо или зарегистрировать зависимую основную сборку взаимодействия в реестре Windows, или воспользоваться параметром **/reference**, чтобы программа Tlbimp.exe обнаружила зависимую библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="2fb46-123">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="2fb46-124">Также можно включить несколько версий библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2fb46-124">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="2fb46-125">Инструкции см. в разделе [Практическое руководство. Включение нескольких версий библиотек типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="2fb46-125">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="2fb46-126">Пример</span><span class="sxs-lookup"><span data-stu-id="2fb46-126">Example</span></span>

<span data-ttu-id="2fb46-127">В приведенном ниже примере выполняется импорт библиотеки типов COM `LibUtil.tlb` и подписание сборки `LibUtil.dll` строгим именем с помощью файла ключа `CompanyA.snk`.</span><span class="sxs-lookup"><span data-stu-id="2fb46-127">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="2fb46-128">Так как имя пространства имен не указано, в этом примере создается пространство имен по умолчанию (`LibUtil`).</span><span class="sxs-lookup"><span data-stu-id="2fb46-128">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="2fb46-129">Чтобы имя было более понятным (соответствовало правилу именования *ИмяПоставщика*.*ИмяБиблиотеки*), в приведенном ниже примере переопределяются имена файла сборки и пространства имен, используемые по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2fb46-129">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="2fb46-130">В приведенном ниже примере выполняется импорт библиотеки `MyLib.tlb`, которая ссылается на `CompanyA.LibUtil.dll`, и подписание сборки `CompanyB.MyLib.dll` строгим именем с помощью файла ключа `CompanyB.snk`.</span><span class="sxs-lookup"><span data-stu-id="2fb46-130">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="2fb46-131">Пространство имен `CompanyB.MyLib` переопределяет пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2fb46-131">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="2fb46-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2fb46-132">See also</span></span>

- [<span data-ttu-id="2fb46-133">Практическое руководство. Регистрация основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="2fb46-133">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)
