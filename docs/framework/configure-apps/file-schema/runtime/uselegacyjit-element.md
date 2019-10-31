---
title: Элемент <useLegacyJit>
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: 47aacb629dc234d9aeaab1ef6e6844fbbe5dbfdb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115110"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="d7acd-102">Элемент \<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="d7acd-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="d7acd-103">Определяет, использует ли среда CLR устаревший 64-разрядный JIT-компилятор для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="d7acd-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="d7acd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d7acd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d7acd-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="d7acd-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d7acd-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент uselegacyjit >**</span><span class="sxs-lookup"><span data-stu-id="d7acd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7acd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7acd-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="d7acd-108">Имя элемента `useLegacyJit` учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="d7acd-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7acd-109">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="d7acd-109">Attributes and elements</span></span>

<span data-ttu-id="d7acd-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d7acd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7acd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d7acd-111">Attributes</span></span>  
  
| <span data-ttu-id="d7acd-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d7acd-112">Attribute</span></span> | <span data-ttu-id="d7acd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d7acd-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="d7acd-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="d7acd-114">Required attribute.</span></span><br><br><span data-ttu-id="d7acd-115">Указывает, использует ли среда выполнения устаревший JIT-компилятор 64.</span><span class="sxs-lookup"><span data-stu-id="d7acd-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="d7acd-116">Включенный атрибут</span><span class="sxs-lookup"><span data-stu-id="d7acd-116">enabled attribute</span></span>  
  
| <span data-ttu-id="d7acd-117">значения</span><span class="sxs-lookup"><span data-stu-id="d7acd-117">Value</span></span> | <span data-ttu-id="d7acd-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d7acd-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="d7acd-119">0</span><span class="sxs-lookup"><span data-stu-id="d7acd-119">0</span></span>     | <span data-ttu-id="d7acd-120">Среда CLR использует новый 64-разрядный компилятор JIT, входящий в .NET Framework 4,6 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d7acd-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="d7acd-121">1</span><span class="sxs-lookup"><span data-stu-id="d7acd-121">1</span></span>     | <span data-ttu-id="d7acd-122">Среда CLR использует устаревший 64-разрядный компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="d7acd-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="d7acd-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d7acd-123">Child elements</span></span>

<span data-ttu-id="d7acd-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="d7acd-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d7acd-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d7acd-125">Parent elements</span></span>  
  
| <span data-ttu-id="d7acd-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="d7acd-126">Element</span></span>         | <span data-ttu-id="d7acd-127">Описание</span><span class="sxs-lookup"><span data-stu-id="d7acd-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="d7acd-128">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d7acd-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="d7acd-129">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d7acd-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="d7acd-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="d7acd-130">Remarks</span></span>  

<span data-ttu-id="d7acd-131">Начиная с .NET Framework 4,6, среда CLR по умолчанию использует новый 64-разрядный компилятор для JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="d7acd-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="d7acd-132">В некоторых случаях это может привести к различию в поведении кода приложения, скомпилированного JIT-компилятором в предыдущей версии 64-разрядного компилятора JIT.</span><span class="sxs-lookup"><span data-stu-id="d7acd-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="d7acd-133">Установив атрибут `enabled` элемента `<useLegacyJit>` в значение `1`, можно отключить новый 64-разрядный компилятор JIT, а затем скомпилировать приложение, используя устаревший JIT-компилятор с 64.</span><span class="sxs-lookup"><span data-stu-id="d7acd-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7acd-134">Элемент `<useLegacyJit>` влияет только на 64-разрядную JIT компиляцию.</span><span class="sxs-lookup"><span data-stu-id="d7acd-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="d7acd-135">Компиляция с 32-разрядным компилятором JIT не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="d7acd-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="d7acd-136">Вместо использования параметра файла конфигурации можно включить устаревший 64-разрядный компилятор JIT в двух других случаях:</span><span class="sxs-lookup"><span data-stu-id="d7acd-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="d7acd-137">Задание переменной среды</span><span class="sxs-lookup"><span data-stu-id="d7acd-137">Setting an environment variable</span></span>

  <span data-ttu-id="d7acd-138">Задайте для переменной среды `COMPLUS_useLegacyJit` значение `0` (используйте новый 64-разрядный компилятор JIT) или `1` (используйте более раннюю версию JIT-компилятора 64):</span><span class="sxs-lookup"><span data-stu-id="d7acd-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="d7acd-139">Переменная среды имеет *глобальную область*, что означает влияние на все приложения, выполняемые на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d7acd-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="d7acd-140">Если значение задано, оно может быть переопределено параметром файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d7acd-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="d7acd-141">Имя переменной среды не учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="d7acd-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="d7acd-142">Добавление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="d7acd-142">Adding a registry key</span></span>

  <span data-ttu-id="d7acd-143">Можно включить устаревший 64-разрядный компилятор JIT, добавив `REG_DWORD` значение в `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` или в `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` ключ в реестре.</span><span class="sxs-lookup"><span data-stu-id="d7acd-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="d7acd-144">Значение имеет имя `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="d7acd-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="d7acd-145">Если значение равно 0, используется новый компилятор.</span><span class="sxs-lookup"><span data-stu-id="d7acd-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="d7acd-146">Если значение равно 1, то включен устаревший JIT-компилятор 64.</span><span class="sxs-lookup"><span data-stu-id="d7acd-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="d7acd-147">Имя значения реестра обрабатывается без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="d7acd-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="d7acd-148">Добавление значения в ключ `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` влияет на все приложения, выполняющиеся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d7acd-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="d7acd-149">Добавление значения в ключ `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` влияет на все приложения, запущенные текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="d7acd-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="d7acd-150">Если на компьютере настроено несколько учетных записей пользователей, затрагиваются только приложения, запущенные текущим пользователем, если только значение не будет добавлено в разделы реестра для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="d7acd-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="d7acd-151">Добавление элемента `<useLegacyJit>` в файл конфигурации переопределяет параметры реестра, если они есть.</span><span class="sxs-lookup"><span data-stu-id="d7acd-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7acd-152">Пример</span><span class="sxs-lookup"><span data-stu-id="d7acd-152">Example</span></span>  

<span data-ttu-id="d7acd-153">Следующий файл конфигурации отключает компиляцию с помощью нового 64-разрядного компилятора JIT, а вместо этого использует устаревший JIT-компилятор с 64.</span><span class="sxs-lookup"><span data-stu-id="d7acd-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7acd-154">См. также</span><span class="sxs-lookup"><span data-stu-id="d7acd-154">See also</span></span>

- [<span data-ttu-id="d7acd-155">Элемент > среды выполнения \<</span><span class="sxs-lookup"><span data-stu-id="d7acd-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="d7acd-156">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="d7acd-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="d7acd-157">Устранение рисков. Новый 64-разрядный JIT-компилятор</span><span class="sxs-lookup"><span data-stu-id="d7acd-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
