---
title: -warn (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: 5b05e944a37e16fc1fcc422271be00c09a271a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602403"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="0ebc0-102">-warn (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="0ebc0-102">-warn (C# Compiler Options)</span></span>
<span data-ttu-id="0ebc0-103">Параметр **-warn** задает уровень предупреждений, которые должны отображаться компилятором.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-103">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ebc0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ebc0-104">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="0ebc0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0ebc0-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="0ebc0-106">При меньших значениях уровня предупреждений отображаются только самые серьезные предупреждения. Чем выше значение, тем больше предупреждений будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-106">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="0ebc0-107">Допускаются значения от 0 до 4:</span><span class="sxs-lookup"><span data-stu-id="0ebc0-107">Valid values are 0-4:</span></span>  
  
|<span data-ttu-id="0ebc0-108">Уровень предупреждений</span><span class="sxs-lookup"><span data-stu-id="0ebc0-108">Warning level</span></span>|<span data-ttu-id="0ebc0-109">Значение</span><span class="sxs-lookup"><span data-stu-id="0ebc0-109">Meaning</span></span>|  
|-------------------|-------------|  
|<span data-ttu-id="0ebc0-110">0</span><span class="sxs-lookup"><span data-stu-id="0ebc0-110">0</span></span>|<span data-ttu-id="0ebc0-111">Отключает вывод всех предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-111">Turns off emission of all warning messages.</span></span>|  
|<span data-ttu-id="0ebc0-112">1</span><span class="sxs-lookup"><span data-stu-id="0ebc0-112">1</span></span>|<span data-ttu-id="0ebc0-113">Отображает серьезные предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-113">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="0ebc0-114">2</span><span class="sxs-lookup"><span data-stu-id="0ebc0-114">2</span></span>|<span data-ttu-id="0ebc0-115">Отображает предупреждения уровня 1, а также некоторые менее серьезные предупреждения, в том числе связанные со скрытием членов класса.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-115">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="0ebc0-116">3</span><span class="sxs-lookup"><span data-stu-id="0ebc0-116">3</span></span>|<span data-ttu-id="0ebc0-117">Отображает предупреждения уровня 2, а также некоторые менее серьезные предупреждения, в том числе связанные с выражениями, которые всегда возвращают значение `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-117">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="0ebc0-118">4 (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0ebc0-118">4 (the default)</span></span>|<span data-ttu-id="0ebc0-119">Отображает все предупреждения уровня 3, а также информационные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-119">Displays all level 3 warnings plus informational warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebc0-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="0ebc0-120">Remarks</span></span>  
 <span data-ttu-id="0ebc0-121">Чтобы получить сведения об ошибке или предупреждении, выполните поиск по соответствующему коду в указателе справочной системы.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-121">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="0ebc0-122">Дополнительные сведения о других способах получить информацию об ошибках и предупреждениях см. в разделе [Ошибки компилятора C#](../compiler-messages/index.md).</span><span class="sxs-lookup"><span data-stu-id="0ebc0-122">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="0ebc0-123">Параметр [-warnaserror](./warnaserror-compiler-option.md) позволяет обрабатывать все предупреждения как ошибки.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-123">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="0ebc0-124">Параметр [-nowarn](./nowarn-compiler-option.md) позволяет отключать определенные предупреждения.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-124">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="0ebc0-125">**-w** является краткой формой **-warn**.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-125">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0ebc0-126">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0ebc0-126">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="0ebc0-127">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-127">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="0ebc0-128">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-128">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="0ebc0-129">Измените свойство **Порог предупреждений**.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-129">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="0ebc0-130">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ebc0-130">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ebc0-131">Пример</span><span class="sxs-lookup"><span data-stu-id="0ebc0-131">Example</span></span>  
 <span data-ttu-id="0ebc0-132">Компиляция файла `in.cs` с отображением только предупреждений уровня 1:</span><span class="sxs-lookup"><span data-stu-id="0ebc0-132">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ebc0-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ebc0-133">See also</span></span>

- [<span data-ttu-id="0ebc0-134">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="0ebc0-134">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="0ebc0-135">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="0ebc0-135">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
