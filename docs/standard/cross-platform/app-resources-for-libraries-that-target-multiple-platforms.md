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
ms.openlocfilehash: b32c2e354ea48e25ddb0aa561eb576cbfd89e3fb
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204741"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Ресурсы приложений для библиотек, предназначенных для нескольких платформ
Можно использовать тип проекта [Переносимая библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) .NET Framework, чтобы обеспечить доступ к ресурсам в библиотеках классов из нескольких платформ. Этот тип проекта доступен в Visual Studio 2012 и предназначен для переносимого подмножества библиотеки классов .NET Framework. Использование переносимой библиотеки классов гарантирует, что доступ к библиотеке можно получить из классических приложений, приложений Silverlight, Windows Phone приложений и приложений Магазина Windows 8. x.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 Проект переносимой библиотеки классов делает неограниченным подмножество типов в пространстве имен <xref:System.Resources>, доступном для приложения, но позволяет использовать класс <xref:System.Resources.ResourceManager> для получения ресурсов. Однако при создании приложения с помощью Visual Studio необходимо использовать строго типизированную оболочку, созданную Visual Studio, а не класс <xref:System.Resources.ResourceManager> непосредственно.

 Чтобы создать строго типизированную оболочку в Visual Studio, установите **Модификатор доступа** основного файла ресурсов в конструкторе ресурсов Visual Studio в значение **Public**. При этом создастся файл [имя_файла_ресурсов].designer.cs или [имя_файла_ресурсов].designer.vb, содержащий строго типизированную оболочку ResourceManager. Дополнительные сведения об использовании обертки ресурсов со строгой типизацией см. в подразделе «Создание класса ресурсов со строгой типизацией» раздела [Resgen. exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) .

## <a name="resource-manager-in-the-portable-class-library"></a>диспетчер ресурсов в переносимой библиотеке классов
 В проекте переносимой библиотеки классов весь доступ к ресурсам обрабатывается классом <xref:System.Resources.ResourceManager>. Поскольку типы в пространстве имен <xref:System.Resources>, такие как <xref:System.Resources.ResourceReader> и <xref:System.Resources.ResourceSet>, недоступны из проекта переносимой библиотеки классов, они не могут использоваться для доступа к ресурсам.

 Проект переносимой библиотеки классов включает четыре <xref:System.Resources.ResourceManager> членов, перечисленных в следующей таблице. Эти конструкторы и методы позволяют создать экземпляр объекта <xref:System.Resources.ResourceManager> и извлечь строковые ресурсы.

|Член`ResourceManager`|Описание|
|------------------------------|-----------------|
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Создает экземпляр <xref:System.Resources.ResourceManager> для доступа к именованному файлу ресурсов, найденному в заданной сборке.|
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Создает экземпляр <xref:System.Resources.ResourceManager>, соответствующий указанному типу.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Извлекает именованный ресурс для текущих языка и региональных параметров.|
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Извлекает именованный ресурс, относящийся к указанным языку и региональным параметрам.|

 Исключение других <xref:System.Resources.ResourceManager> членов из переносимой библиотеки классов означает, что сериализованные объекты, нестроковые данные и изображения не могут быть извлечены из файла ресурсов. Чтобы использовать ресурсы из переносимой библиотеки классов, необходимо сохранить все данные объекта в виде строки. Например, числовые значения можно сохранять в файле ресурсов, преобразуя в строки. Их также можно извлекать и затем преобразовывать обратно в числа с помощью метода `Parse` или `TryParse` числового типа данных. Изображения и другие двоичные данные можно преобразовать в строковое представление, вызвав метод <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>, и восстановить их в массив байтов с помощью метода <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.

## <a name="the-portable-class-library-and-windows-store-apps"></a>Переносимая библиотека классов и приложения для Магазина Windows
 Проекты переносимых библиотек классов хранят ресурсы в файлах. resx, которые затем компилируются в файлы. Resources и внедряются в основную сборку или во вспомогательные сборки во время компиляции. С другой стороны, для приложений Магазина Windows 8. x требуется, чтобы ресурсы хранились в файлах. resw, которые затем компилируются в один файл индекса ресурсов пакета (PRI). Однако, несмотря на несовместимые форматы файлов, Переносимая библиотека классов будет работать в приложении Магазина Windows 8. x.

 Чтобы использовать библиотеку классов из приложения Магазина Windows 8. x, добавьте ссылку на него в проект приложения Магазина Windows. Visual Studio прозрачно извлечет ресурсы из сборки в RESW-файл и будет использовать его для создания PRI-файла, из которого среда выполнения Windows может извлекать ресурсы. Во время выполнения среда выполнения Windows выполняет код в переносимой библиотеке классов, но извлекают ресурсы переносимой библиотеки классов из PRI файла.

 Если проект переносимой библиотеки классов включает локализованные ресурсы, для их развертывания используется модель «звезда», как и для библиотеки в классическом приложении. Чтобы использовать основной файл ресурсов и все локализованные файлы ресурсов в приложении для Магазина Windows 8. x, добавьте ссылку на основную сборку. Во время компиляции Visual Studio извлекает ресурсы из основного файла ресурсов и всех локализованных файлов ресурсов в отдельные файлы RESW. Затем файлы. resw компилируются в один PRI-файл, к которому среда выполнения Windows обращается во время выполнения.

<a name="NonLoc"></a>
## <a name="example-non-localized-portable-class-library"></a>Пример: нелокализованная Переносимая библиотека классов
 В следующем примере простой, нелокализованной переносимой библиотеки классов используются ресурсы для хранения имен столбцов и для определения количества символов, резервируемых для табличных данных. В этом примере используется файл с именем LibResources.resx для хранения строковых ресурсов, перечисленных в следующей таблице.

|Имя ресурса|Значение ресурса|
|-------------------|--------------------|
|Born|Birthdate|
|BornLength|12|
|Hired|Дата приема на работу|
|HiredLength|12|
|ИДЕНТИФИКАТОР|ИДЕНТИФИКАТОР|
|ID.Length|12|
|Имя|Имя|
|NameLength|25|
|Заголовок|Employee Database|

 В следующем коде определяется класс `UILibrary`, использующий оболочку диспетчер ресурсов с именем `resources`, созданную Visual Studio, когда **Модификатор доступа** для файла изменяется на **Public**. Класс UILibrary анализирует строковые данные по мере необходимости. . Обратите внимание, что класс находится в пространстве имен `MyCompany.Employees`.

 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Для этого требуется ссылка на UILibrary. dll для добавления в проект консольного приложения.

 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]

 В следующем коде показано, как к классу `UILibrary` и его ресурсам можно получить доступ из приложения Магазина Windows 8. x. Для этого требуется ссылка на UILibrary. dll для добавления в проект приложения Магазина Windows.

 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]

## <a name="example-localized-portable-class-library"></a>Пример: локализованная Переносимая библиотека классов
 В следующем примере переносимой библиотеки классов содержатся ресурсы для языков и региональных параметров "французский (Франция)" и "Английский (США)". Язык и региональные параметры по умолчанию для английского языка (США). его ресурсы показаны в таблице в [предыдущем разделе](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Файл ресурсов для французского (Франция) языка и региональных параметров называется LibResources.fr-FR.resx и состоит из строковых ресурсов, перечисленных в представленной ниже таблице. Исходный код для класса `UILibrary` такой же, как и в предыдущем разделе.

|Имя ресурса|Значение ресурса|
|-------------------|--------------------|
|Born|Date de naissance|
|BornLength|20|
|Hired|Дата ембаучé|
|HiredLength|16|
|ИДЕНТИФИКАТОР|ИДЕНТИФИКАТОР|
|Имя|Nom|
|Заголовок|Base de доннéес des емплойéс|

 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Для этого требуется ссылка на UILibrary. dll для добавления в проект консольного приложения.

 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]

 В следующем коде показано, как к классу `UILibrary` и его ресурсам можно получить доступ из приложения Магазина Windows 8. x. Для этого требуется ссылка на UILibrary. dll для добавления в проект приложения Магазина Windows. В коде используется статическое свойство `ApplicationLanguages.PrimaryLanguageOverride`, чтобы в качестве предпочтительного языка приложения указать французский язык.

 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также:

- <xref:System.Resources.ResourceManager>
- [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)
- [Упаковка и развертывание ресурсов](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
