---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968084"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="41f85-101">Имена файлов манифеста ресурса</span><span class="sxs-lookup"><span data-stu-id="41f85-101">Resource manifest file names</span></span>

<span data-ttu-id="41f85-102">Начиная с .NET Core 3.0, создание имени файла манифеста ресурса изменилось.</span><span class="sxs-lookup"><span data-stu-id="41f85-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41f85-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="41f85-103">Version introduced</span></span>

<span data-ttu-id="41f85-104">3.0</span><span class="sxs-lookup"><span data-stu-id="41f85-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="41f85-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="41f85-105">Change description</span></span>

<span data-ttu-id="41f85-106">До .NET Core 3.0, когда для файла ресурсов ( *.resx*) в файле проекта MSBuild были заданы метаданные [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile), созданным именем манифеста было *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="41f85-107">Если параметр [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) не был задан, созданным именем манифеста было *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="41f85-108">Начиная с .NET Core 3.0, при совмещении файла *.resx* с одноименным исходным файлом, например, в приложениях Windows Forms, имя манифеста ресурсов генерируется из полного имени первого типа в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="41f85-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="41f85-109">Например, если *Type.cs* размещается вместе с *Type.resx*, создается имя манифеста *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="41f85-110">Однако если изменить какие-либо атрибуты в свойстве `EmbeddedResource` для файла *.resx*, имя созданного файла манифеста может отличаться:</span><span class="sxs-lookup"><span data-stu-id="41f85-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="41f85-111">Если для свойства `EmbeddedResource` задан атрибут `LogicalName`, это значение используется в качестве имени файла манифеста ресурса.</span><span class="sxs-lookup"><span data-stu-id="41f85-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="41f85-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="41f85-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="41f85-113">**Имя созданного файла манифеста ресурса**: *SomeName.resources* (независимо от имени файла *.resx*, языка и региональных параметров или любых других метаданных).</span><span class="sxs-lookup"><span data-stu-id="41f85-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="41f85-114">Если `LogicalName` не установлено, но в свойстве `EmbeddedResource` задано атрибут `ManifestResourceName`, то в качестве имени файла манифеста ресурса используется его значение в сочетании с расширением файла *.resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="41f85-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="41f85-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="41f85-116">**Имя созданного файла манифеста ресурса**: *SomeName.resources* или *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="41f85-117">Если предыдущие правила не применяются, а атрибут `DependentUpon` в элементе `EmbeddedResource` установлен для исходного файла, то в имени файла манифеста ресурса используется тип имени первого класса в исходном файле.</span><span class="sxs-lookup"><span data-stu-id="41f85-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="41f85-118">Точнее, имя сгенерированного файла — *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="41f85-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="41f85-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="41f85-120">**Имя созданного файла манифеста ресурса**: *Namespace.Classname.resources* или *Namespace.Classname.fr-FR.resources* (где `Namespace.Classname` — имя первого класса в *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="41f85-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="41f85-121">Если предыдущие правила не применяются, `EmbeddedResourceUseDependentUponConvention` является `true` (по умолчанию для .NET Core), и есть исходный файл, совмещенный с файлом *.resx*, который имеет то же самое базовое имя файла, файл *.resx* становится зависимым от совпадающего исходного файла, а сгенерированное имя будет таким же, как и в предыдущем правиле.</span><span class="sxs-lookup"><span data-stu-id="41f85-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="41f85-122">Это правило "настройки по умолчанию" для проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="41f85-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="41f85-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="41f85-123">Examples:</span></span>
  
  <span data-ttu-id="41f85-124">Файлы *MyTypes.cs* и *MyTypes.resx* или *MyTypes.fr-FR.resx* находятся в одной папке.</span><span class="sxs-lookup"><span data-stu-id="41f85-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="41f85-125">**Имя созданного файла манифеста ресурса**: *Namespace.Classname.resources* или *Namespace.Classname.fr-FR.resources* (где `Namespace.Classname` — имя первого класса в *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="41f85-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="41f85-126">Если ни одно из предыдущих правил не применяется, то именем сгенерированного файла манифеста ресурса будет *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="41f85-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="41f85-127">Относительный путь — это значение атрибута `Link` элемента `EmbeddedResource`, если он установлен.</span><span class="sxs-lookup"><span data-stu-id="41f85-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="41f85-128">В противном случае относительный путь — это значение атрибута `Identity` элемента `EmbeddedResource`.</span><span class="sxs-lookup"><span data-stu-id="41f85-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="41f85-129">В Visual Studio это путь от корня проекта до файла в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="41f85-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41f85-130">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="41f85-130">Recommended action</span></span>

<span data-ttu-id="41f85-131">Если вы не удовлетворены сгенерированными именами манифеста, вы можете выполнить приведенные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="41f85-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="41f85-132">Измените метаданные файла ресурса в соответствии с одним из описанных выше правил именования.</span><span class="sxs-lookup"><span data-stu-id="41f85-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="41f85-133">Задайте для `EmbeddedResourceUseDependentUponConvention` значение `false` в вашем файле проекта, чтобы полностью отказаться от нового соглашения:</span><span class="sxs-lookup"><span data-stu-id="41f85-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="41f85-134">Если присутствуют атрибуты `LogicalName` или `ManifestResourceName`, то их значения все равно будут использоваться для сгенерированного имени файла.</span><span class="sxs-lookup"><span data-stu-id="41f85-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="41f85-135">Категория</span><span class="sxs-lookup"><span data-stu-id="41f85-135">Category</span></span>

<span data-ttu-id="41f85-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="41f85-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41f85-137">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="41f85-137">Affected APIs</span></span>

<span data-ttu-id="41f85-138">Н/Д</span><span class="sxs-lookup"><span data-stu-id="41f85-138">N/A</span></span>
