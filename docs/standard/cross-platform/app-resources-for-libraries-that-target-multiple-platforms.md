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
ms.openlocfilehash: a6c589a393ccfb5610a19776af6e33e4046bf5d3
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45569278"
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>Ресурсы приложений для библиотек, предназначенных для нескольких платформ
Можно использовать .NET Framework [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) тип, чтобы убедиться, что ресурсы в библиотеках классов может осуществляться из нескольких платформ проекта. Проект этого типа доступен в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] и нацелен на переносимое подмножество библиотеки классов .NET Framework. Использование [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] гарантирует доступность библиотеки из настольных приложений, приложений Silverlight, Windows Phone и [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]
  
 Проект [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] предоставляет приложению только очень ограниченное подмножество типов в пространстве имен <xref:System.Resources>, но позволяет использовать класс <xref:System.Resources.ResourceManager> для извлечения ресурсов. Однако при создании приложения с помощью Visual Studio необходимо использовать строго типизированную оболочку, созданную Visual Studio, а не класс <xref:System.Resources.ResourceManager> непосредственно.  
  
 Для создания строго типизированной оболочки в Visual Studio установите основного файла ресурсов **модификатор доступа** в конструкторе ресурсов Visual Studio для **открытый**. При этом создастся файл [имя_файла_ресурсов].designer.cs или [имя_файла_ресурсов].designer.vb, содержащий строго типизированную оболочку ResourceManager. Дополнительные сведения об использовании строго типизированной оболочки ресурсов см. в разделе «Создание строго типизированного класса ресурсов» в [Resgen.exe (генератор файлов ресурсов)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) раздела.  
  
## <a name="resource-manager-in-the-includenetportableincludesnet-portable-mdmd"></a>Диспетчер ресурсов в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 В проекте [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] весь доступ к ресурсам обрабатывается классом <xref:System.Resources.ResourceManager>. Поскольку типы в пространстве имен <xref:System.Resources>, в частности <xref:System.Resources.ResourceReader> и <xref:System.Resources.ResourceSet>, не доступны из проекта [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], их нельзя использовать для доступа к ресурсам.  
  
 Проект [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] содержит четыре члена <xref:System.Resources.ResourceManager>, перечисленных в представленной ниже таблице. Эти конструкторы и методы позволяют создать экземпляр объекта <xref:System.Resources.ResourceManager> и извлечь строковые ресурсы.  
  
|Член `ResourceManager`|Описание|  
|------------------------------|-----------------|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|Создает экземпляр <xref:System.Resources.ResourceManager> для доступа к именованному файлу ресурсов, найденному в заданной сборке.|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|Создает экземпляр <xref:System.Resources.ResourceManager>, соответствующий указанному типу.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|Извлекает именованный ресурс для текущих языка и региональных параметров.|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|Извлекает именованный ресурс, относящийся к указанным языку и региональным параметрам.|  
  
 Исключение других членов <xref:System.Resources.ResourceManager> из [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] означает, что сериализованные объекты, нестроковые данные и изображения невозможно извлечь из файла ресурсов. Чтобы использовать ресурсы из [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], необходимо хранить все данные объекта в строковом формате. Например, числовые значения можно сохранять в файле ресурсов, преобразуя в строки. Их также можно извлекать и затем преобразовывать обратно в числа с помощью метода `Parse` или `TryParse` числового типа данных. Изображения и другие двоичные данные можно преобразовать в строковое представление, вызвав метод <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType>, и восстановить их в массив байтов с помощью метода <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType>.  
  
## <a name="the-includenetportableincludesnet-portable-mdmd-and-windows-store-apps"></a>[!INCLUDE[net_portable](../../../includes/net-portable-md.md)] и приложения для Магазина Windows  
 В проектах [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] ресурсы хранятся в файлах с расширением RESX, которые затем компилируются в файлы с расширением RESOURCES и встраиваются в основную или вспомогательные сборки во время компиляции. Приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], с другой стороны, требуют, чтобы ресурсы хранились в файлах с расширением RESW, которые затем компилируются в единый файл индекса ресурсов пакета (PRI). Однако несмотря на несовместимые форматы файлов, [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] будет работать в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 Чтобы использовать библиотеку классов из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], добавьте ссылку на него в проекте приложения для Магазина Windows. Visual Studio прозрачно извлечет ресурсы из сборки в файл RESW и использует его для создания файла PRI, из которого [!INCLUDE[wrt](../../../includes/wrt-md.md)] может извлекать ресурсы. Во время выполнения [!INCLUDE[wrt](../../../includes/wrt-md.md)] выполняет код в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], но извлекает ресурсы переносимой библиотеки классов из файла PRI.  
  
 Если проект [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] содержит локализованные ресурсы, то для их развертывания используется модель "звезда" так же, как и для библиотеки в настольном приложении. Для использования основного файла ресурсов и любых локализованных файлов ресурсов в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] следует добавить ссылку на основную сборку. Во время компиляции Visual Studio извлекает ресурсы из основного файла ресурсов и всех локализованных файлов ресурсов в отдельные файлы RESW. Затем Visual Studio компилирует файлы RESW в единый файл PRI, к которому [!INCLUDE[wrt](../../../includes/wrt-md.md)] обращается во время выполнения.  
  
<a name="NonLoc"></a>   
## <a name="example-non-localized-includenetportableincludesnet-portable-mdmd"></a>Пример: нелокализованная [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 В следующем простом примере нелокализованная [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] использует ресурсы для хранения имен столбцов и определения числа символов, которые следует зарезервировать для табличных данных. В этом примере используется файл с именем LibResources.resx для хранения строковых ресурсов, перечисленных в следующей таблице.  
  
|Имя ресурса|Значение ресурса|  
|-------------------|--------------------|  
|Born|Birthdate|  
|BornLength|12|  
|Hired|Дата приема на работу|  
|HiredLength|12|  
|Идентификатор|Идентификатор|  
|ID.Length|12|  
|Имя|Имя|  
|NameLength|25|  
|Заголовок|Employee Database|  
  
 В следующем коде определяется `UILibrary` класс, который использует оболочку диспетчера ресурсов с именем `resources` создается средой Visual Studio при **модификатор доступа** файла изменена на **открытый** . Класс UILibrary анализирует строковые данные по мере необходимости. . Обратите внимание, что класс находится в пространстве имен `MyCompany.Employees`.  
  
 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]  
  
 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Для этого требуется добавить в проект консольного приложения ссылку на файл UILIbrary.dll.  
  
 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]  
  
 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Для этого требуется добавить в проект приложения для Магазина Windows ссылку на файл UILIbrary.dll.  
  
 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]  
  
## <a name="example-localized-includenetportableincludesnet-portable-mdmd"></a>Пример: локализованная [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 Следующий пример локализованной [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] содержит ресурсы французского (Франция) и английского (США) языков и региональных параметров. Английского языка (США) является языком по умолчанию приложения; его ресурсы показаны в таблице в [выше](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc). Файл ресурсов для французского (Франция) языка и региональных параметров называется LibResources.fr-FR.resx и состоит из строковых ресурсов, перечисленных в представленной ниже таблице. Исходный код для класса `UILibrary` такой же, как и в предыдущем разделе.  
  
|Имя ресурса|Значение ресурса|  
|-------------------|--------------------|  
|Born|Date de naissance|  
|BornLength|20|  
|Hired|Date embauché|  
|HiredLength|16|  
|Идентификатор|Идентификатор|  
|Имя|Nom|  
|Заголовок|Base de données des employés|  
  
 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из консольного приложения. Для этого требуется добавить в проект консольного приложения ссылку на файл UILIbrary.dll.  
  
 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]  
  
 В следующем примере кода показано, как к классу `UILibrary` и его ресурсам можно обращаться из приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Для этого требуется добавить в проект приложения для Магазина Windows ссылку на файл UILIbrary.dll. В коде используется статическое свойство `ApplicationLanguages.PrimaryLanguageOverride`, чтобы в качестве предпочтительного языка приложения указать французский язык.  
  
 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Resources.ResourceManager>  
- [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)  
- [Упаковка и развертывание ресурсов](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
