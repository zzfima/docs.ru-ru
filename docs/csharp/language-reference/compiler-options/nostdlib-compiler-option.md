---
title: -nostdlib (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 70007c74efe9a41bdfc15e8fa7daf3c8fc0221ed
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484139"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="a832e-102">-nostdlib (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a832e-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="a832e-103">Параметр **-nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.</span><span class="sxs-lookup"><span data-stu-id="a832e-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="a832e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a832e-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="a832e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a832e-105">Remarks</span></span>

<span data-ttu-id="a832e-106">Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.</span><span class="sxs-lookup"><span data-stu-id="a832e-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="a832e-107">Если вы не укажете параметр **-nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="a832e-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="a832e-108">Указание **-nostdlib** дает тот же результат, что и указание **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="a832e-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="a832e-109">Установка параметра компилятора в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a832e-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="a832e-110">Следующие инструкции применимы только к Visual Studio 2015 (и более ранних версий).</span><span class="sxs-lookup"><span data-stu-id="a832e-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="a832e-111">Свойство сборки **Не ссылаться на mscorlib.dll** не существует в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a832e-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="a832e-112">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="a832e-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="a832e-113">Щелкните страницу свойств **сборки** .</span><span class="sxs-lookup"><span data-stu-id="a832e-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="a832e-114">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="a832e-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="a832e-115">Измените свойство **Не ссылаться на mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="a832e-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="a832e-116">Установка данного параметра компилятора программным способом</span><span class="sxs-lookup"><span data-stu-id="a832e-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="a832e-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="a832e-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a832e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a832e-118">See Also</span></span>

- [<span data-ttu-id="a832e-119">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="a832e-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
