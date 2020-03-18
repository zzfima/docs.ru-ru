---
title: Соображения относительно версии и обновления для разработчиков на C#
description: Добавление в библиотеку новых компонентов языка может повлиять на код, который использует эту библиотеку.
ms.date: 09/19/2018
ms.openlocfilehash: 3ffe2f6fd64a391fddf28233dccb022c95851884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398151"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="5cb21-103">Соображения относительно версии и обновления для разработчиков на C#</span><span class="sxs-lookup"><span data-stu-id="5cb21-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="5cb21-104">Совместимость очень важна при добавлении новых функций языка C#.</span><span class="sxs-lookup"><span data-stu-id="5cb21-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="5cb21-105">В большинстве случаев существующий код сможет компилироваться в новой версии компилятора безо всяких проблем.</span><span class="sxs-lookup"><span data-stu-id="5cb21-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="5cb21-106">Особое внимание требуется в тех случаях, когда в библиотеку добавляются новые возможности языка.</span><span class="sxs-lookup"><span data-stu-id="5cb21-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="5cb21-107">Например, если вы создаете новую библиотеку с функциями из последней версии, но ее должны использовать приложения, созданные в предыдущих версиях компилятора.</span><span class="sxs-lookup"><span data-stu-id="5cb21-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="5cb21-108">Или же вы обновляете существующую библиотеку, но многие ваши пользователи пока используют старые версии.</span><span class="sxs-lookup"><span data-stu-id="5cb21-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="5cb21-109">Принимая решения о внедрении новых функций, необходимо учесть два аспекта совместимости: на уровне исходного кода и на уровне двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="5cb21-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="5cb21-110">Изменения, совместимые на уровне двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="5cb21-110">Binary compatible changes</span></span>

<span data-ttu-id="5cb21-111">Изменения библиотеки считаются **совместимыми на уровне двоичных файлов**, если новую версию библиотеки можно использовать без повторной сборки приложении и других библиотек, которые ее используют.</span><span class="sxs-lookup"><span data-stu-id="5cb21-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="5cb21-112">В этом сценарии не нужно перестраивать зависимые сборки и (или) вносить изменения в исходный код.</span><span class="sxs-lookup"><span data-stu-id="5cb21-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="5cb21-113">Измерения, совместимые на уровне двоичных файлов, всегда совместимы и на уровне исходного кода.</span><span class="sxs-lookup"><span data-stu-id="5cb21-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="5cb21-114">Изменения, совместимые на уровне исходного кода</span><span class="sxs-lookup"><span data-stu-id="5cb21-114">Source compatible changes</span></span>

<span data-ttu-id="5cb21-115">Изменения библиотеки будут **совместимыми на уровне исходного кода**, если для приложений и библиотек, которые используют новую библиотеку, не потребуется изменять исходный код, но для правильной работы нужно заново скомпилировать их с новой версией.</span><span class="sxs-lookup"><span data-stu-id="5cb21-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="5cb21-116">Несовместимые изменения</span><span class="sxs-lookup"><span data-stu-id="5cb21-116">Incompatible changes</span></span>

<span data-ttu-id="5cb21-117">Если изменение не является совместимым ни **на уровне исходного кода**, ни **на уровне двоичных файлов**, для зависимых приложений и библиотек потребуется изменить исходный код и заново скомпилировать их.</span><span class="sxs-lookup"><span data-stu-id="5cb21-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="5cb21-118">Оценка существующих библиотек</span><span class="sxs-lookup"><span data-stu-id="5cb21-118">Evaluate your library</span></span>

<span data-ttu-id="5cb21-119">Эти концепции совместимости влияют на компоненты библиотеки с атрибутами public и protected, но не на ее внутреннюю реализацию.</span><span class="sxs-lookup"><span data-stu-id="5cb21-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="5cb21-120">Любые новые возможности внутри библиотеки всегда **совместимы на уровне двоичных файлов**.</span><span class="sxs-lookup"><span data-stu-id="5cb21-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="5cb21-121">К **совместимым на уровне двоичных файлов** изменениям относится любой новый синтаксис, который создает такой же скомпилированный код любых открытых (public) объявлений, как и со старым синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="5cb21-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="5cb21-122">Например, замена метода на член, воплощающий выражение, будет **совместимым на уровне двоичных файлов изменением**.</span><span class="sxs-lookup"><span data-stu-id="5cb21-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="5cb21-123">Исходный код:</span><span class="sxs-lookup"><span data-stu-id="5cb21-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="5cb21-124">Новый код:</span><span class="sxs-lookup"><span data-stu-id="5cb21-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="5cb21-125">Изменения, **совместимые на уровне исходного кода**, создают новый синтаксис, который изменяет скомпилированный код одного или нескольких открытых (public) членов таким образом, который сохраняет его совместимость со всеми существующими вызывающими объектами.</span><span class="sxs-lookup"><span data-stu-id="5cb21-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="5cb21-126">Например, если подпись метода ранее передавала параметр по значению, а теперь содержит `in` с параметром по ссылке, такое изменение будет совместимым на уровне исходного кода, но не на уровне двоичных файлов:</span><span class="sxs-lookup"><span data-stu-id="5cb21-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="5cb21-127">Исходный код:</span><span class="sxs-lookup"><span data-stu-id="5cb21-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="5cb21-128">Новый код:</span><span class="sxs-lookup"><span data-stu-id="5cb21-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="5cb21-129">Во всех статьях [о новых возможностях](index.md) всегда указано, является ли новая функция для открытых объявлений совместимый на уровне исходного кода или на уровне двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="5cb21-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
