---
ms.openlocfilehash: 16ee73bfc0ab33b04ea3e2fa6d0eec521a9b8634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968084"
---
### <a name="resource-manifest-file-names"></a>Имена файлов манифеста ресурса

Начиная с .NET Core 3.0, создание имени файла манифеста ресурса изменилось.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="change-description"></a>Описание изменений

До .NET Core 3.0, когда для файла ресурсов ( *.resx*) в файле проекта MSBuild были заданы метаданные [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile), созданным именем манифеста было *Namespace.Classname.resources*. Если параметр [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) не был задан, созданным именем манифеста было *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.

Начиная с .NET Core 3.0, при совмещении файла *.resx* с одноименным исходным файлом, например, в приложениях Windows Forms, имя манифеста ресурсов генерируется из полного имени первого типа в исходном файле. Например, если *Type.cs* размещается вместе с *Type.resx*, создается имя манифеста *Namespace.Classname.resources*. Однако если изменить какие-либо атрибуты в свойстве `EmbeddedResource` для файла *.resx*, имя созданного файла манифеста может отличаться:

- Если для свойства `EmbeddedResource` задан атрибут `LogicalName`, это значение используется в качестве имени файла манифеста ресурса.

  Примеры

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  **Имя созданного файла манифеста ресурса**: *SomeName.resources* (независимо от имени файла *.resx*, языка и региональных параметров или любых других метаданных).

- Если `LogicalName` не установлено, но в свойстве `EmbeddedResource` задано атрибут `ManifestResourceName`, то в качестве имени файла манифеста ресурса используется его значение в сочетании с расширением файла *.resources*.

  Примеры

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  **Имя созданного файла манифеста ресурса**: *SomeName.resources* или *SomeName.fr-FR.resources*.

- Если предыдущие правила не применяются, а атрибут `DependentUpon` в элементе `EmbeddedResource` установлен для исходного файла, то в имени файла манифеста ресурса используется тип имени первого класса в исходном файле. Точнее, имя сгенерированного файла — *Namespace.Classname\[.Culture].resources*.

  Примеры

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  **Имя созданного файла манифеста ресурса**: *Namespace.Classname.resources* или *Namespace.Classname.fr-FR.resources* (где `Namespace.Classname` — имя первого класса в *MyTypes.cs*).

- Если предыдущие правила не применяются, `EmbeddedResourceUseDependentUponConvention` является `true` (по умолчанию для .NET Core), и есть исходный файл, совмещенный с файлом *.resx*, который имеет то же самое базовое имя файла, файл *.resx* становится зависимым от совпадающего исходного файла, а сгенерированное имя будет таким же, как и в предыдущем правиле. Это правило "настройки по умолчанию" для проектов .NET Core.
  
  Примеры
  
  Файлы *MyTypes.cs* и *MyTypes.resx* или *MyTypes.fr-FR.resx* находятся в одной папке.
  
  **Имя созданного файла манифеста ресурса**: *Namespace.Classname.resources* или *Namespace.Classname.fr-FR.resources* (где `Namespace.Classname` — имя первого класса в *MyTypes.cs*).

- Если ни одно из предыдущих правил не применяется, то именем сгенерированного файла манифеста ресурса будет *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*. Относительный путь — это значение атрибута `Link` элемента `EmbeddedResource`, если он установлен. В противном случае относительный путь — это значение атрибута `Identity` элемента `EmbeddedResource`. В Visual Studio это путь от корня проекта до файла в обозревателе решений.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы не удовлетворены сгенерированными именами манифеста, вы можете выполнить приведенные ниже действия.

- Измените метаданные файла ресурса в соответствии с одним из описанных выше правил именования.

- Задайте для `EmbeddedResourceUseDependentUponConvention` значение `false` в вашем файле проекта, чтобы полностью отказаться от нового соглашения:

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > Если присутствуют атрибуты `LogicalName` или `ManifestResourceName`, то их значения все равно будут использоваться для сгенерированного имени файла.

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д
