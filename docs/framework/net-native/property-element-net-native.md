---
title: Элемент <Property> (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: b9bc89804a872dddf1a56c2a3dadc9c3df4f5fd1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128215"
---
# <a name="property-element-net-native"></a><span data-ttu-id="15af5-102">Элемент > свойства \<(.NET Native)</span><span class="sxs-lookup"><span data-stu-id="15af5-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="15af5-103">Применяет политику отражения среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="15af5-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15af5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15af5-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15af5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15af5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="15af5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="15af5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15af5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15af5-107">Attributes</span></span>  
  
|<span data-ttu-id="15af5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="15af5-108">Attribute</span></span>|<span data-ttu-id="15af5-109">Тип атрибута</span><span class="sxs-lookup"><span data-stu-id="15af5-109">Attribute type</span></span>|<span data-ttu-id="15af5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="15af5-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="15af5-111">Общее</span><span class="sxs-lookup"><span data-stu-id="15af5-111">General</span></span>|<span data-ttu-id="15af5-112">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15af5-112">Required attribute.</span></span> <span data-ttu-id="15af5-113">Задает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="15af5-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="15af5-114">Отражение</span><span class="sxs-lookup"><span data-stu-id="15af5-114">Reflection</span></span>|<span data-ttu-id="15af5-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15af5-115">Optional attribute.</span></span> <span data-ttu-id="15af5-116">Определяет запрос для получения сведений о свойстве или перечисляет свойство, но не включает динамический доступ во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15af5-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="15af5-117">Отражение</span><span class="sxs-lookup"><span data-stu-id="15af5-117">Reflection</span></span>|<span data-ttu-id="15af5-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15af5-118">Optional attribute.</span></span> <span data-ttu-id="15af5-119">Управляет доступом среды выполнения к свойству для включения динамического программирования.</span><span class="sxs-lookup"><span data-stu-id="15af5-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="15af5-120">Эта политика гарантирует, что свойство можно задать или получить динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15af5-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="15af5-121">Сериализация</span><span class="sxs-lookup"><span data-stu-id="15af5-121">Serialization</span></span>|<span data-ttu-id="15af5-122">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="15af5-122">Optional attribute.</span></span> <span data-ttu-id="15af5-123">Управляет доступом среды выполнения к свойству, чтобы включить экземпляры типов, предназначенных для сериализации в таких библиотеках, как сериализатор Newtonsoft JSON или для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="15af5-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="15af5-124">Name - атрибут</span><span class="sxs-lookup"><span data-stu-id="15af5-124">Name attribute</span></span>  
  
|<span data-ttu-id="15af5-125">значения</span><span class="sxs-lookup"><span data-stu-id="15af5-125">Value</span></span>|<span data-ttu-id="15af5-126">Описание</span><span class="sxs-lookup"><span data-stu-id="15af5-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="15af5-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="15af5-127">*method_name*</span></span>|<span data-ttu-id="15af5-128">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="15af5-128">The property name.</span></span> <span data-ttu-id="15af5-129">Тип свойства определяется родительским элементом [\<Type>](type-element-net-native.md) или [\<TypeInstantiation>](typeinstantiation-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="15af5-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="15af5-130">Все остальные атрибуты</span><span class="sxs-lookup"><span data-stu-id="15af5-130">All other attributes</span></span>  
  
|<span data-ttu-id="15af5-131">значения</span><span class="sxs-lookup"><span data-stu-id="15af5-131">Value</span></span>|<span data-ttu-id="15af5-132">Описание</span><span class="sxs-lookup"><span data-stu-id="15af5-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="15af5-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="15af5-133">*policy_setting*</span></span>|<span data-ttu-id="15af5-134">Параметр, применяемый к этому типу политики для свойства.</span><span class="sxs-lookup"><span data-stu-id="15af5-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="15af5-135">Допустимые значения: `Auto`, `Excluded`, `Included` и `Required`.</span><span class="sxs-lookup"><span data-stu-id="15af5-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="15af5-136">Дополнительные сведения см. в разделе [Параметры политики директив среды выполнения](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="15af5-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15af5-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15af5-137">Child Elements</span></span>  
 <span data-ttu-id="15af5-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="15af5-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15af5-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15af5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="15af5-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="15af5-140">Element</span></span>|<span data-ttu-id="15af5-141">Описание</span><span class="sxs-lookup"><span data-stu-id="15af5-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15af5-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="15af5-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="15af5-143">Применяет политику отражения к типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="15af5-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="15af5-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="15af5-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="15af5-145">Применяет политику отражения к сконструированному универсальному типу и всем его членам.</span><span class="sxs-lookup"><span data-stu-id="15af5-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15af5-146">Заметки</span><span class="sxs-lookup"><span data-stu-id="15af5-146">Remarks</span></span>  
 <span data-ttu-id="15af5-147">Если политика свойства не определена явно, оно наследует политику среды выполнения своего родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="15af5-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15af5-148">Пример</span><span class="sxs-lookup"><span data-stu-id="15af5-148">Example</span></span>  
 <span data-ttu-id="15af5-149">В следующем примере используется отражение для создания экземпляров объекта `Book` и отображения значений его свойств.</span><span class="sxs-lookup"><span data-stu-id="15af5-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="15af5-150">Исходный файл default.rd.xml для проекта выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="15af5-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="15af5-151">Файл применяет значение `All` к политике `Activate` для класса `Book`, который предоставляет доступ к конструкторам класса через отражение.</span><span class="sxs-lookup"><span data-stu-id="15af5-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="15af5-152">Политика `Browse` для класса `Book` наследуется от его родительского пространства имен.</span><span class="sxs-lookup"><span data-stu-id="15af5-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="15af5-153">Это свойство имеет значение `Required Public`, что делает метаданные доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15af5-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="15af5-154">Ниже приведен исходный код для этого примера.</span><span class="sxs-lookup"><span data-stu-id="15af5-154">The following is the source code for the example.</span></span> <span data-ttu-id="15af5-155">Переменная `outputBlock` представляет элемент управления <xref:Windows.UI.Xaml.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="15af5-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="15af5-156">Тем не менее компиляция и выполнение этого примера создает исключение [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="15af5-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="15af5-157">Несмотря на то, что мы уже сделали метаданные для типа `Book` доступными, нам не удалось обеспечить динамический доступ к реализациям свойств считывания.</span><span class="sxs-lookup"><span data-stu-id="15af5-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="15af5-158">Эту ошибку можно исправить одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="15af5-158">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="15af5-159">определив политику `Dynamic` для типа `Book` в его элементе [\<Type>](type-element-net-native.md);</span><span class="sxs-lookup"><span data-stu-id="15af5-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="15af5-160">добавив вложенный элемент [\<Property>](property-element-net-native.md) для каждого свойства, считывание которого необходимо вызвать, как это делает следующий файл default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="15af5-160">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="15af5-161">См. также</span><span class="sxs-lookup"><span data-stu-id="15af5-161">See also</span></span>

- [<span data-ttu-id="15af5-162">Справочник по конфигурационному файлу директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="15af5-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="15af5-163">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="15af5-163">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="15af5-164">Параметры политики директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="15af5-164">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
