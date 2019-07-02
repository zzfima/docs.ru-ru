---
title: Ресурсы приложений для библиотек, предназначенных для нескольких платформ
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e846f45b55ac09d6ce6af4f3223c3bdba1dc83ba
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506012"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Ресурсы приложений для библиотек, предназначенных для нескольких платформ
Можно использовать .NET Framework [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) тип, чтобы убедиться, что ресурсы в библиотеках классов может осуществляться из нескольких платформ проекта. Этот тип проекта доступен в Visual Studio 2012 и нацелена на переносимое подмножество библиотеки классов .NET Framework. Использование переносимой библиотеки классов гарантирует, что библиотека может осуществляться из классических приложений, приложений Silverlight, приложения Windows Phone и [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Проект переносимой библиотеки классов делает только очень ограниченное подмножество типов в <xref:System.Resources> пространство имен, доступное для приложения, но его можно будет использовать <xref:System.Resources.ResourceManager> класса для извлечения ресурсов. Однако при создании приложения с помощью Visual Studio необходимо использовать строго типизированную оболочку, созданную Visual Studio, а не класс <xref:System.Resources.ResourceManager> непосредственно.

 Для создания строго типизированной оболочки в Visual Studio установите основного файла ресурсов **модификатор доступа** в конструкторе ресурсов Visual Studio для **открытый**. При этом создастся файл [имя_файла_ресурсов].designer.cs или [имя_файла_ресурсов].designer.vb, содержащий строго типизированную оболочку ResourceManager. Дополнительные сведения об использовании строго типизированной оболочки ресурсов см. в разделе «Создание строго типизированного класса ресурсов» в [Resgen.exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) раздела.

## <a name="resource-manager-in-the-portable-class-library"></a>Диспетчер ресурсов в переносимой библиотеки классов
 В проекте переносимой библиотеки классов, обрабатывается весь доступ к ресурсам <xref:System.Resources.ResourceManager> класса. Поскольку типы в <xref:System.Resources> пространства имен, такие как <xref:System.Resources.ResourceReader> и <xref:System.Resources.ResourceSet>, являются не доступен из проекта переносимой библиотеки классов, они не может использоваться для доступа к ресурсам.

 Проект переносимой библиотеки классов включает четыре <xref:System.Resources.ResourceManager> элементы, перечисленные в следующей таблице. Эти конструкторы и методы позволяют создать экземпляр объекта <xref:System.Resources.ResourceManager> и извлечь строковые ресурсы.

|Член`ResourceManager`|Описание|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Создает экземпляр <xref:System.Resources.ResourceManager> для доступа к именованному файлу ресурсов, найденному в заданной сборке.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Создает экземпляр <xref:System.Resources.ResourceManager>, соответствующий указанному типу.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Извлекает именованный ресурс для текущих языка и региональных параметров.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Извлекает именованный ресурс, относящийся к указанным языку и региональным параметрам.|

 Исключение других <xref:System.Resources.ResourceManager> членов из переносимой библиотеки классов означает, что сериализованные объекты, нестроковые данные и изображения невозможно извлечь из файла ресурсов. Чтобы использовать ресурсы из переносимой библиотеки классов, следует хранить все данные объекта в виде строки. Например, числовые значения можно сохранять в файле ресурсов, преобразуя в строки. Их также можно извлекать и затем преобразовывать обратно в числа с помощью метода `Parse` или `TryParse` числового типа данных. Изображения и другие двоичные данные можно преобразовать в строковое представление, вызвав метод <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>, и восстановить их в массив байтов с помощью метода <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>Переносимая библиотека классов и приложениях Windows Store
 Проекты переносимой библиотеки классов хранения ресурсов в RESX-файлах, которые затем компилируются в файлы ресурсов и встроить в основную сборку или вспомогательные сборки во время компиляции. Приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], с другой стороны, требуют, чтобы ресурсы хранились в файлах с расширением RESW, которые затем компилируются в единый файл индекса ресурсов пакета (PRI). Тем не менее, несмотря на несовместимые форматы файлов, переносимой библиотеки классов будет работать [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения.

 Чтобы использовать библиотеку классов из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], добавьте ссылку на него в проекте приложения для Магазина Windows. Visual Studio прозрачно извлечет ресурсы из сборки в resw-файл и использовать его для создания файла PRI, из которого среда выполнения Windows может извлекать ресурсы. Во время выполнения среда выполнения Windows выполняет код в переносимой библиотеки классов, но он извлекает ресурсы переносимой библиотеки классов из файла PRI.

 Если проект переносимой библиотеки классов содержит локализованные ресурсы, используется модель концентратор и спица будет развернуто, так же, как и для библиотеки в настольном приложении. Для использования основного файла ресурсов и любых локализованных файлов ресурсов в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] следует добавить ссылку на основную сборку. Во время компиляции Visual Studio извлекает ресурсы из основного файла ресурсов и всех локализованных файлов ресурсов в отдельные файлы RESW. Он компилирует файлы resw в единый файл PRI, который обращается к среде выполнения Windows во время выполнения.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Пример Нелокализованное переносимой библиотеки классов
 В следующем примере переносимой библиотеки классов простой, нелокализованное использует ресурсы для хранения имен столбцов и определить количество символов, которое следует зарезервировать для табличных данных. В этом примере используется файл с именем LibResources.resx для хранения строковых ресурсов, перечисленных в следующей таблице.

|Имя ресурса|Значение ресурса|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Дата приема на работу|
|HiredLength|12|
|ID|ID|
|ID.Length|12|
|name|name|
|NameLength|25|
|Заголовок|Employee Database|

 В следующем коде определяется `UILibrary` класс, который использует оболочку диспетчера ресурсов с именем `resources` создается средой Visual Studio при **модификатор доступа** файла изменена на **открытый** . Класс UILibrary анализирует строковые данные по мере необходимости. . Обратите внимание, что класс находится в пространстве имен `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Он требует ссылку на файл UILibrary.dll добавляемый проект консольного приложения.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Он требует ссылку на файл UILibrary.dll для добавления в проект приложения Windows Store.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Пример Локализованные переносимой библиотеки классов
 В следующем примере локализованные переносимой библиотеки классов включает ресурсы для французского (Франция) и русский (Россия) языков и региональных параметров. Английского языка (США) является языком по умолчанию приложения; его ресурсы показаны в таблице в [выше](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Файл ресурсов для французского (Франция) языка и региональных параметров называется LibResources.fr-FR.resx и состоит из строковых ресурсов, перечисленных в представленной ниже таблице. Исходный код для класса `UILibrary` такой же, как и в предыдущем разделе.

|Имя ресурса|Значение ресурса|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Дата embauché|
|HiredLength|16|
|ID|ID|
|name|Nom|
|Заголовок|Базовый de données des employés|

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Он требует ссылку на файл UILibrary.dll добавляемый проект консольного приложения.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Он требует ссылку на файл UILibrary.dll для добавления в проект приложения Windows Store. В коде используется статическое свойство `ApplicationLanguages.PrimaryLanguageOverride`, чтобы в качестве предпочтительного языка приложения указать французский язык.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Resources.ResourceManager>
- [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)
- [Упаковка и развертывание ресурсов](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
