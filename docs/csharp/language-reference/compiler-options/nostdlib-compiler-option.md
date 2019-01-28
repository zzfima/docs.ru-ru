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
ms.openlocfilehash: cf87d8d2ac4531142288a8637f7fbeb9139382ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545833"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="69416-102">-nostdlib (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="69416-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="69416-103">Параметр **-nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.</span><span class="sxs-lookup"><span data-stu-id="69416-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="69416-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69416-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="69416-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="69416-105">Remarks</span></span>

<span data-ttu-id="69416-106">Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.</span><span class="sxs-lookup"><span data-stu-id="69416-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="69416-107">Если вы не укажете параметр **-nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **-nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="69416-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="69416-108">Указание **-nostdlib** дает тот же результат, что и указание **-nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="69416-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="69416-109">Установка параметра компилятора в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69416-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="69416-110">Следующие инструкции применимы только к Visual Studio 2015 (и более ранних версий).</span><span class="sxs-lookup"><span data-stu-id="69416-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="69416-111">Свойство сборки **Не ссылаться на mscorlib.dll** не существует в Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="69416-111">The **Do not reference mscorlib.dll** build property doesn't exist in Visual Studio 2017.</span></span>

1. <span data-ttu-id="69416-112">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="69416-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="69416-113">Щелкните страницу свойств **сборки** .</span><span class="sxs-lookup"><span data-stu-id="69416-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="69416-114">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="69416-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="69416-115">Измените свойство **Не ссылаться на mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="69416-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="69416-116">Установка данного параметра компилятора программным способом</span><span class="sxs-lookup"><span data-stu-id="69416-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="69416-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="69416-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="69416-118">См. также</span><span class="sxs-lookup"><span data-stu-id="69416-118">See also</span></span>

- [<span data-ttu-id="69416-119">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="69416-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
