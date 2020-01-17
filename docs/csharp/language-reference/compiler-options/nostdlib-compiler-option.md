---
title: -nostdlib (параметры компилятора C#)
ms.date: 12/20/2019
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: ad8a2b5fc87dd7beee86d96331cf3961315be533
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345081"
---
# <a name="-nostdlib-c-compiler-options"></a><span data-ttu-id="d04bd-102">-nostdlib (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="d04bd-102">-nostdlib (C# Compiler Options)</span></span>

<span data-ttu-id="d04bd-103">Параметр **-nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.</span><span class="sxs-lookup"><span data-stu-id="d04bd-103">**-nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

## <a name="syntax"></a><span data-ttu-id="d04bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d04bd-104">Syntax</span></span>

```console
-nostdlib[+ | -]
```

## <a name="remarks"></a><span data-ttu-id="d04bd-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d04bd-105">Remarks</span></span>

<span data-ttu-id="d04bd-106">Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.</span><span class="sxs-lookup"><span data-stu-id="d04bd-106">Use this option if you want to define or create your own System namespace and objects.</span></span>

<span data-ttu-id="d04bd-107">Если вы не укажете параметр **-nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **-nostdlib-** ).</span><span class="sxs-lookup"><span data-stu-id="d04bd-107">If you do not specify **-nostdlib**, mscorlib.dll is imported into your program (same as specifying **-nostdlib-**).</span></span> <span data-ttu-id="d04bd-108">Указание **-nostdlib** дает тот же результат, что и указание **-nostdlib+** .</span><span class="sxs-lookup"><span data-stu-id="d04bd-108">Specifying **-nostdlib** is the same as specifying **-nostdlib+**.</span></span>

### <a name="to-set-this-compiler-option-in-visual-studio"></a><span data-ttu-id="d04bd-109">Установка параметра компилятора в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d04bd-109">To set this compiler option in Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="d04bd-110">Следующие инструкции применимы только к Visual Studio 2015 (и более ранних версий).</span><span class="sxs-lookup"><span data-stu-id="d04bd-110">The following instructions apply to Visual Studio 2015 (and earlier versions) only.</span></span> <span data-ttu-id="d04bd-111">Свойство сборки **Не ссылаться на mscorlib.dll** отсутствует в более поздних версиях Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d04bd-111">The **Do not reference mscorlib.dll** build property doesn't exist in newer versions of Visual Studio.</span></span>

1. <span data-ttu-id="d04bd-112">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="d04bd-112">Open the **Properties** page for the project.</span></span>

2. <span data-ttu-id="d04bd-113">Щелкните страницу свойств **сборки** .</span><span class="sxs-lookup"><span data-stu-id="d04bd-113">Click the **Build** properties page.</span></span>

3. <span data-ttu-id="d04bd-114">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="d04bd-114">Click the **Advanced** button.</span></span>

4. <span data-ttu-id="d04bd-115">Измените свойство **Не ссылаться на mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="d04bd-115">Modify the **Do not reference mscorlib.dll** property.</span></span>

### <a name="to-set-this-compiler-option-programmatically"></a><span data-ttu-id="d04bd-116">Установка данного параметра компилятора программным способом</span><span class="sxs-lookup"><span data-stu-id="d04bd-116">To set this compiler option programmatically</span></span>

<span data-ttu-id="d04bd-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="d04bd-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="d04bd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d04bd-118">See also</span></span>

- [<span data-ttu-id="d04bd-119">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="d04bd-119">C# Compiler Options</span></span>](./index.md)
