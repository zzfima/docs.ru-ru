---
title: Устранение рисков. Новый 64-разрядный JIT-компилятор
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
ms.openlocfilehash: dd8c2c6b3cfa919970f68f2faae2044568f6c9ac
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457910"
---
# <a name="mitigation-new-64-bit-jit-compiler"></a><span data-ttu-id="153bb-102">Устранение рисков. Новый 64-разрядный JIT-компилятор</span><span class="sxs-lookup"><span data-stu-id="153bb-102">Mitigation: New 64-bit JIT Compiler</span></span>
<span data-ttu-id="153bb-103">Начиная с .NET Framework 4.6 среда выполнения включает в себя новый 64-разрядный JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="153bb-103">Starting with the .NET Framework 4.6, the runtime includes a new 64-bit JIT compiler for just-in-time compilation.</span></span> <span data-ttu-id="153bb-104">Это изменение не влияет на компиляцию с помощью 32-разрядного JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="153bb-104">This change does not affect compilation with the  32-bit JIT compiler.</span></span>  
  
## <a name="unexpected-behavior-or-exceptions"></a><span data-ttu-id="153bb-105">Непредвиденное поведение или исключения</span><span class="sxs-lookup"><span data-stu-id="153bb-105">Unexpected behavior or exceptions</span></span>  
 <span data-ttu-id="153bb-106">В некоторых случаях компиляция с помощью нового 64-разрядного JIT-компилятора приводит к исключению среды выполнения или к поведению, которое не наблюдается при выполнении кода, скомпилированного старым 64-разрядным JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="153bb-106">In some cases, compilation with the new 64-bit JIT compiler results in a runtime exception or in behavior that is not observed when executing code compiled by the older 64-bit JIT compiler.</span></span> <span data-ttu-id="153bb-107">Известные различия включают в себя следующее.</span><span class="sxs-lookup"><span data-stu-id="153bb-107">The known differences include the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="153bb-108">Все эти известные проблемы устранены в новом 64-разрядном компиляторе на платформе .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="153bb-108">All of these known issues have been addressed in the new 64-bit compiler released with the .NET Framework 4.6.2.</span></span> <span data-ttu-id="153bb-109">Большинство проблем было также устранено в выпусках обновлений платформы .NET Framework 4.6 и 4.6.1, включенных в состав обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="153bb-109">Most have also been addressed in service releases of the .NET Framework 4.6 and 4.6.1 that are included with Windows Update.</span></span> <span data-ttu-id="153bb-110">Эти проблемы можно устранить, обеспечив актуальность используемой версии Windows или обновив платформу до версии .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="153bb-110">You can eliminate these issues by ensuring that your version of Windows is up to date, or by upgrading to the .NET Framework 4.6.2.</span></span>  
  
- <span data-ttu-id="153bb-111">При определенных условиях операция распаковки может вызывать исключение <xref:System.NullReferenceException> в сборках выпусков с включенной оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="153bb-111">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span>  
  
- <span data-ttu-id="153bb-112">В некоторых случаях выполнение рабочего кода в большом теле метода может вызывать исключение <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="153bb-112">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span>  
  
- <span data-ttu-id="153bb-113">При определенных условиях в сборках выпусков передаваемые методу структуры обрабатываются как ссылочные типы, а не типы значений.</span><span class="sxs-lookup"><span data-stu-id="153bb-113">Under certain conditions, structures passed to a method are treated as reference types rather than value types in Release builds.</span></span> <span data-ttu-id="153bb-114">Одним из проявлений этой проблемы является отображение отдельных элементов коллекции в непредвиденном порядке.</span><span class="sxs-lookup"><span data-stu-id="153bb-114">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span>  
  
- <span data-ttu-id="153bb-115">При определенных условиях сравнение значений <xref:System.UInt16> с установленным старшим битом выполняется неверно, если включена оптимизация.</span><span class="sxs-lookup"><span data-stu-id="153bb-115">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span>  
  
- <span data-ttu-id="153bb-116">При определенных условиях, особенно при инициализации значений массивов, инициализация памяти инструкцией <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL может инициализировать память неправильным значением.</span><span class="sxs-lookup"><span data-stu-id="153bb-116">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="153bb-117">Это может привести либо к необработанному исключению, либо к неправильным выходным данным.</span><span class="sxs-lookup"><span data-stu-id="153bb-117">This can result either in an unhandled exception or incorrect output.</span></span>  
  
- <span data-ttu-id="153bb-118">В некоторых редких случаях условная поразрядная проверка может возвращать неверное значение типа <xref:System.Boolean> или вызывать исключение, если включены оптимизации компилятора.</span><span class="sxs-lookup"><span data-stu-id="153bb-118">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span>  
  
- <span data-ttu-id="153bb-119">При определенных условиях, если инструкция `if` используется для проверки условия перед входом в блок `try` и на выходе из блока `try`, и такое же условие вычисляется в блоке `catch` или `finally`, новый 64-разрядный JIT-компилятор удаляет условие `if` из блока `catch` или `finally` при оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="153bb-119">Under certain conditions, if an `if` statement is used to test for a condition before entering  a `try` block and in the exit from the `try` block, and the same condition is evaluated in the `catch` or `finally` block, the new 64-bit JIT compiler removes the `if` condition from the `catch` or `finally` block when it optimizes code.</span></span> <span data-ttu-id="153bb-120">В результате код внутри инструкции `if` в блоке `catch` или `finally` выполняется безусловно.</span><span class="sxs-lookup"><span data-stu-id="153bb-120">As a result, code inside the `if` statement in the `catch` or `finally` block is executed unconditionally.</span></span>  
  
<a name="General"></a>   
## <a name="mitigation-of-known-issues"></a><span data-ttu-id="153bb-121">Устранение известных проблем</span><span class="sxs-lookup"><span data-stu-id="153bb-121">Mitigation of known issues</span></span>  
 <span data-ttu-id="153bb-122">При возникновении перечисленных выше проблем их можно решить, выполнив одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="153bb-122">If you encounter the issues listed above, you can address them by doing any of the following:</span></span>  
  
- <span data-ttu-id="153bb-123">Обновление до .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="153bb-123">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="153bb-124">Новый 64-разрядный компилятор, входящий в состав .NET Framework 4.6.2, устраняет все эти известные проблемы.</span><span class="sxs-lookup"><span data-stu-id="153bb-124">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span>  
  
- <span data-ttu-id="153bb-125">Обновление Windows до актуального состояния при запуске Центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="153bb-125">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="153bb-126">Обновления служб до .NET Framework 4.6 и 4.6.1 решают все эти проблемы, кроме исключения <xref:System.NullReferenceException> при распаковке-преобразовании.</span><span class="sxs-lookup"><span data-stu-id="153bb-126">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span>  
  
- <span data-ttu-id="153bb-127">Компиляция с помощью старого 64-разрядного JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="153bb-127">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="153bb-128">Дополнительные сведения о том, как это сделать, см. в разделе [Устранение других проблем](#Other).</span><span class="sxs-lookup"><span data-stu-id="153bb-128">See the [Mitigation of other issues](#Other) section for more information on how to do this.</span></span>  
  
<a name="Other"></a>   
## <a name="mitigation-of-other-issues"></a><span data-ttu-id="153bb-129">Устранение других проблем</span><span class="sxs-lookup"><span data-stu-id="153bb-129">Mitigation of other issues</span></span>  
 <span data-ttu-id="153bb-130">При возникновении любых других различий в поведении между кодом, скомпилированным с помощью старого и нового 64-разрядных JIT-компиляторов, или между отладочной и окончательной версиями приложения, которые обе скомпилированы новым 64-разрядным JIT-компилятором, можно выполнить следующие действия для компиляции приложения с помощью старого 64-разрядного JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="153bb-130">If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span>  
  
- <span data-ttu-id="153bb-131">Для каждого отдельного приложения можно добавить элемент [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) в файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="153bb-131">On a per-application basis, you can add the [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="153bb-132">Следующее действие отключает компиляцию с помощью нового 64-разрядного JIT-компилятора и вместо этого использует устаревший 64-разрядный JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="153bb-132">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
- <span data-ttu-id="153bb-133">Для каждого отдельного пользователя можно добавить значение `REG_DWORD` с именем `useLegacyJit` в раздел реестра `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`.</span><span class="sxs-lookup"><span data-stu-id="153bb-133">On a per-user basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="153bb-134">Значение 1 включает устаревший 64-разрядный JIT-компилятор; значение 0 отключает его и включает новый 64-разрядный JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="153bb-134">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
- <span data-ttu-id="153bb-135">Для каждого отдельного компьютера можно добавить значение `REG_DWORD` с именем `useLegacyJit` в раздел реестра `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`.</span><span class="sxs-lookup"><span data-stu-id="153bb-135">On a per-machine basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="153bb-136">Значение 1 включает устаревший 64-разрядный JIT-компилятор; значение 0 отключает его и включает новый 64-разрядный JIT-компилятор.</span><span class="sxs-lookup"><span data-stu-id="153bb-136">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
 <span data-ttu-id="153bb-137">Можно также сообщить нам об обнаруженной проблеме, обратившись в службу [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span><span class="sxs-lookup"><span data-stu-id="153bb-137">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153bb-138">См. также</span><span class="sxs-lookup"><span data-stu-id="153bb-138">See also</span></span>

- [<span data-ttu-id="153bb-139">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="153bb-139">Application compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="153bb-140">Элемент \<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="153bb-140">\<useLegacyJit> Element</span></span>](../configure-apps/file-schema/runtime/uselegacyjit-element.md)
