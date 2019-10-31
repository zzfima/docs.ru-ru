---
title: Элемент <supportPortability>
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
ms.openlocfilehash: 63c309a8a93c1d31ed8f73a495cf5154c3590d56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115652"
---
# <a name="supportportability-element"></a><span data-ttu-id="c4c22-102">\<supportPortability > элемент</span><span class="sxs-lookup"><span data-stu-id="c4c22-102">\<supportPortability> Element</span></span>
<span data-ttu-id="c4c22-103">Указывает, что приложение может ссылаться на ту же сборку в двух различных реализациях .NET Framework, отключая поведение по умолчанию, которое рассматривает сборки как эквивалент для переносимости приложения.</span><span class="sxs-lookup"><span data-stu-id="c4c22-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
<span data-ttu-id="c4c22-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4c22-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4c22-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="c4c22-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c4c22-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="c4c22-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="c4c22-107">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \<supportPortability **>**</span><span class="sxs-lookup"><span data-stu-id="c4c22-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<supportPortability>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c22-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4c22-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4c22-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c4c22-109">Attributes and Elements</span></span>  

<span data-ttu-id="c4c22-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4c22-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4c22-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4c22-111">Attributes</span></span>  
  
|<span data-ttu-id="c4c22-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c4c22-112">Attribute</span></span>|<span data-ttu-id="c4c22-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c22-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4c22-114">PKT</span><span class="sxs-lookup"><span data-stu-id="c4c22-114">PKT</span></span>|<span data-ttu-id="c4c22-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c4c22-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4c22-116">Указывает токен открытого ключа для затронутой сборки в виде строки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="c4c22-117">enabled</span><span class="sxs-lookup"><span data-stu-id="c4c22-117">enabled</span></span>|<span data-ttu-id="c4c22-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c4c22-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c4c22-119">Указывает, должна ли быть включена поддержка переносимости между реализациями указанной .NET Framework сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c4c22-120">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="c4c22-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="c4c22-121">значения</span><span class="sxs-lookup"><span data-stu-id="c4c22-121">Value</span></span>|<span data-ttu-id="c4c22-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c22-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4c22-123">true</span><span class="sxs-lookup"><span data-stu-id="c4c22-123">true</span></span>|<span data-ttu-id="c4c22-124">Включить поддержку переносимости между реализациями указанной .NET Framework сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="c4c22-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c4c22-125">This is the default.</span></span>|  
|<span data-ttu-id="c4c22-126">Ложь</span><span class="sxs-lookup"><span data-stu-id="c4c22-126">false</span></span>|<span data-ttu-id="c4c22-127">Отключение поддержки переносимости между реализациями указанной .NET Framework сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="c4c22-128">Это позволяет приложению иметь ссылки на несколько реализаций указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4c22-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4c22-129">Child Elements</span></span>  

<span data-ttu-id="c4c22-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c4c22-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4c22-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4c22-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c4c22-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="c4c22-132">Element</span></span>|<span data-ttu-id="c4c22-133">Описание</span><span class="sxs-lookup"><span data-stu-id="c4c22-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4c22-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4c22-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4c22-135">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="c4c22-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="c4c22-136">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="c4c22-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4c22-137">Заметки</span><span class="sxs-lookup"><span data-stu-id="c4c22-137">Remarks</span></span>  

<span data-ttu-id="c4c22-138">Начиная с .NET Framework 4, поддержка предоставляется автоматически для приложений, которые могут использовать любую из двух реализаций .NET Framework, например либо реализацию .NET Framework, либо .NET Framework для реализации Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c4c22-138">Beginning with the .NET Framework 4, support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="c4c22-139">Две реализации конкретной .NET Framework сборки считаются эквивалентными связывателем сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="c4c22-140">В нескольких сценариях эта функция переносимости приложений вызывает проблемы.</span><span class="sxs-lookup"><span data-stu-id="c4c22-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="c4c22-141">В этих сценариях для отключения функции можно использовать элемент `<supportPortability>`.</span><span class="sxs-lookup"><span data-stu-id="c4c22-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
<span data-ttu-id="c4c22-142">Одним из таких сценариев является сборка, которая должна ссылаться как на реализацию .NET Framework, так и на .NET Framework для реализации в Silverlight конкретной ссылочной сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="c4c22-143">Например, конструктору XAML, написанному на Windows Presentation Foundation (WPF), может потребоваться ссылка на реализацию WPF настольной системы, для пользовательского интерфейса конструктора и подмножество WPF, включенное в реализацию Silverlight.</span><span class="sxs-lookup"><span data-stu-id="c4c22-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="c4c22-144">По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c22-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="c4c22-145">Этот элемент отключает поведение по умолчанию и обеспечивает успешную компиляцию.</span><span class="sxs-lookup"><span data-stu-id="c4c22-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c4c22-146">Чтобы компилятор мог передать информацию в логику привязки сборки среды CLR, необходимо использовать параметр компилятора `/appconfig`, чтобы указать расположение файла App. config, содержащего этот элемент.</span><span class="sxs-lookup"><span data-stu-id="c4c22-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4c22-147">Пример</span><span class="sxs-lookup"><span data-stu-id="c4c22-147">Example</span></span>  

<span data-ttu-id="c4c22-148">В следующем примере приложение включает ссылки на реализацию .NET Framework и .NET Framework для реализации Silverlight любой .NET Framework сборки, которая существует в обеих реализациях.</span><span class="sxs-lookup"><span data-stu-id="c4c22-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="c4c22-149">Для указания расположения этого файла App. config необходимо использовать параметр компилятора `/appconfig`.</span><span class="sxs-lookup"><span data-stu-id="c4c22-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4c22-150">См. также</span><span class="sxs-lookup"><span data-stu-id="c4c22-150">See also</span></span>

- [<span data-ttu-id="c4c22-151">-appconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c4c22-151">-appconfig (C# Compiler Options)</span></span>](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- <span data-ttu-id="c4c22-152">[Общие сведения об унификации сборок .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4c22-152">[.NET Framework Assembly Unification Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))</span></span>
