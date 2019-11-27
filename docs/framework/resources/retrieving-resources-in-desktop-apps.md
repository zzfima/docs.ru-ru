---
title: Извлечение ресурсов в приложениях для настольных систем
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- resource files, packaging
- application resources, packaging
- localization
- versioning satellite assemblies
- retrieving localized resources
- application resources, deploying
- packaging application resources
- versioning resources
- translating resources into languages
- localizing resources
ms.assetid: eca16922-1c46-4f68-aefe-e7a12283641f
ms.openlocfilehash: 39bb518306b6e76aea1ae4a791fca79fbbb1b6c8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445739"
---
# <a name="retrieving-resources-in-desktop-apps"></a>Извлечение ресурсов в приложениях для настольных систем

При работе с локализованными ресурсами в классических приложениях .NET Framework желательно упаковывать ресурсы для нейтральной или стандартной комбинации языка и региональных параметров в основную сборку и создавать отдельную вспомогательную сборку для каждого языка или каждой комбинации языка и региональных параметров, поддерживаемых вашим приложением. Затем можно использовать класс <xref:System.Resources.ResourceManager> для доступа к именованным ресурсам, как описано в следующем разделе. Если вы решили не внедрять ресурсы в основную и вспомогательные сборки, можно обратиться к двоичным файлам RESOURCES напрямую, как описано в разделе [Извлечение ресурсов из файлов RESOURCES](#from_file) далее в этой статье.  Сведения о получении ресурсов в приложениях для Магазина Windows 8. x см. [в статье Создание и извлечение ресурсов в приложениях для Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140)).  
  
<a name="from_assembly"></a>   
## <a name="retrieving-resources-from-assemblies"></a>Извлечение ресурсов из сборок  
 Класс <xref:System.Resources.ResourceManager> предоставляет доступ к ресурсам во время выполнения. Вы можете использовать метод <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> для извлечения строковых ресурсов и метод <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType> или <xref:System.Resources.ResourceManager.GetStream%2A?displayProperty=nameWithType> для извлечения нестроковых ресурсов. Каждый метод имеет две перегрузки:  
  
- Перегрузка, единственным параметром которой является строка с именем ресурса. Метод пытается извлечь этот ресурс для языка и региональных параметров текущего потока. Дополнительные сведения см. в описании методов <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>и <xref:System.Resources.ResourceManager.GetStream%28System.String%29> .  
  
- Перегрузка, имеющая два параметра: строка с именем ресурса, а также объект <xref:System.Globalization.CultureInfo> , представляющий язык и региональные параметры, для которых требуется извлечь ресурс. Если не удается найти набор ресурсов для данной комбинации языка и региональных параметров, диспетчер ресурсов использует резервные правила для получения соответствующего ресурса. Дополнительные сведения см. в описании методов <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>и <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> .  
  
 Диспетчер ресурсов использует процесс резервных ресурсов, чтобы управлять тем, как приложение извлекает ресурсы, связанные с языком и региональными параметрами. Дополнительные сведения см. в разделе "Процесс использования резервных ресурсов" статьи [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md). Сведения о создании экземпляра объекта <xref:System.Resources.ResourceManager> см. в разделе "Создание экземпляров объекта ResourceManager" статьи о классе <xref:System.Resources.ResourceManager> .  
  
### <a name="retrieving-string-data-an-example"></a>Извлечение строковых данных: пример  
 В следующем примере вызывается метод <xref:System.Resources.ResourceManager.GetString%28System.String%29> для извлечения строковых ресурсов текущего языка и региональных параметров пользовательского интерфейса. Он включает нейтральный строковый ресурс для английского языка (США) и локализованные ресурсы для французского (Франция) и русского (Россия) языков и соответствующих региональных параметров. Следующий ресурс для английского языка (США) находится в файле Strings.txt:  
  
```text
TimeHeader=The current time is  
```  
  
 Ресурс для французского языка (Франция) находится в файле Strings.fr-FR.txt:  
  
```text
TimeHeader=L'heure actuelle est  
```  
  
 Ресурс для русского языка (Россия) находится в файле Strings.ru-RU-txt:  
  
```text
TimeHeader=Текущее время —  
```  
  
 Исходный код этого примера, находящийся в файле GetString.cs для версии C# и GetString.vb для версии Visual Basic, определяет строковый массив, содержащий имя четырех комбинаций языков и региональных параметров: три комбинации, для которых доступны ресурсы, а также комбинацию для испанского языка (Испания). Цикл, который выполняется пять раз, случайным образом выбирает одну из этих комбинаций языков и региональных параметров и присваивает ее свойствам <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> . Затем он вызывает метод <xref:System.Resources.ResourceManager.GetString%28System.String%29> для извлечения локализованной строки, которая отображается вместе с временем дня.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstring.cs#3)]
 [!code-vb[Conceptual.Resources.Retrieving#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstring.vb#3)]  
  
 Следующий пакетный файл (BAT) компилирует этот пример и создает вспомогательные сборки в соответствующих каталогах. Команды приведены для языка и компилятора C#. Для Visual Basic замените `csc` на `vbc`и `GetString.cs` на `GetString.vb`.  
  
```console
resgen strings.txt  
csc GetString.cs -resource:strings.resources  
  
resgen strings.fr-FR.txt  
md fr-FR  
al -embed:strings.fr-FR.resources -culture:fr-FR -out:fr-FR\GetString.resources.dll  
  
resgen strings.ru-RU.txt  
md ru-RU  
al -embed:strings.ru-RU.resources -culture:ru-RU -out:ru-RU\GetString.resources.dll  
```  
  
 Если текущая комбинация языка и региональных параметров пользовательского интерфейса относится к испанскому языку (Испания), обратите внимание, что пример отображает ресурсы на английском языке, так как ресурсы для испанского языка недоступны, а в примере английский язык задан по умолчанию.  
  
### <a name="retrieving-object-data-two-examples"></a>Извлечение данных объекта: два примера  
 Для извлечения данных объекта можно использовать методы <xref:System.Resources.ResourceManager.GetObject%2A> и <xref:System.Resources.ResourceManager.GetStream%2A> . Сюда входят типы-примитивы, сериализуемые объекты и объекты, хранящиеся в двоичном формате (например, изображения).  
  
 В следующем примере метод <xref:System.Resources.ResourceManager.GetStream%28System.String%29> используется для извлечения точечного рисунка, который используется на экране-заставке приложения. Следующий исходный код в файле с именем CreateResources.cs (для C#) или CreateResources.vb (для Visual Basic) создает файл RESX, содержащий сериализованное изображение. В этом случае изображение загружается из файла SplashScreen.jpg; имя файла можно изменить, чтобы использовать собственное изображение.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/createresources.cs#4)]
 [!code-vb[Conceptual.Resources.Retrieving#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/createresources.vb#4)]  
  
 Следующий код извлекает ресурс и отображает изображение в элементе управления <xref:System.Windows.Forms.PictureBox> .  
  
 [!code-csharp[Conceptual.Resources.Retrieving#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/getstream.cs#5)]
 [!code-vb[Conceptual.Resources.Retrieving#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/getstream.vb#5)]  
  
 Для сборки примера на C# можно использовать приведенный ниже пакетный файл. Для Visual Basic замените `csc` на `vbc`, а также расширение файла исходного кода `.cs` на `.vb`.  
  
```console
csc CreateResources.cs  
CreateResources  
  
resgen AppResources.resx  
  
csc GetStream.cs -resource:AppResources.resources  
```  
  
 В следующем примере для десериализации настраиваемого объекта используется метод <xref:System.Resources.ResourceManager.GetObject%28System.String%29?displayProperty=nameWithType> . Пример включает файл исходного кода UIElements.cs (UIElements.vb для Visual Basic), который определяет следующую структуру с именем `PersonTable`. Эта структура предназначена для использования подпрограммой общего отображения таблиц, которая отображает локализованные имена для столбцов таблиц. Обратите внимание, что структура `PersonTable` помечена атрибутом <xref:System.SerializableAttribute> .  
  
 [!code-csharp[Conceptual.Resources.Retrieving#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example.cs#6)]
 [!code-vb[Conceptual.Resources.Retrieving#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#6)]  
  
 Следующий код из файла CreateResources.cs (CreateResources.vb для Visual Basic) создает файл ресурсов XML с именем UIResources.resx, где хранится заголовок таблицы, и объект `PersonTable` , содержащий сведения о приложении, локализуемые для английского языка.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example1.cs#7)]
 [!code-vb[Conceptual.Resources.Retrieving#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example.vb#7)]  
  
 После этого приведенный ниже код из файла GetObject.cs (GetObject.vb) извлекает ресурсы и выводит их на консоль.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example2.cs#8)]
 [!code-vb[Conceptual.Resources.Retrieving#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example2.vb#8)]  
  
 Создать нужный файл ресурсов, сборки и запустить приложение можно, запустив следующий пакетный файл. Необходимо использовать параметр `/r` , чтобы предоставить Resgen.exe ссылку на UIElements.dll для доступа к информации о структуре `PersonTable` . Если используется C#, замените имя компилятора `vbc` на `csc`и расширение `.vb` на `.cs`.  
  
```console
vbc -t:library UIElements.vb  
vbc CreateResources.vb -r:UIElements.dll  
CreateResources  
  
resgen UIResources.resx  -r:UIElements.dll  
vbc GetObject.vb -r:UIElements.dll -resource:UIResources.resources  
  
GetObject.exe  
```  
  
## <a name="versioning-support-for-satellite-assemblies"></a>Поддержка управления версиями для вспомогательных сборок  
 По умолчанию, когда объект <xref:System.Resources.ResourceManager> извлекает запрошенные ресурсы, он ищет вспомогательные сборки с номерами версий, совпадающими с номером версии основной сборки. После развертывания приложения может потребоваться обновить основную сборку или вспомогательные сборки для конкретного ресурса. Платформа .NET Framework обеспечивает поддержку управления версиями как для основной, так и для вспомогательных сборок.  
  
 Атрибут <xref:System.Resources.SatelliteContractVersionAttribute> обеспечивает поддержку управления версиями для главной сборки. Указание этого атрибута для основной сборки приложения позволяет обновить и заново развернуть основную сборку без обновления ее вспомогательных сборок. После обновления основной сборки следует увеличить номер версии основной сборки, а номер версии вспомогательной сборки следует оставить без изменений. Когда диспетчер ресурсов извлекает запрошенные ресурсы, он загружает версию вспомогательной сборки, заданную этим атрибутом.  
  
 Сборки политик издателя обеспечивают поддержку управления версиями для вспомогательных сборок. Вы можете обновить и заново развернуть вспомогательную сборку без обновления основной сборки. После обновления вспомогательной сборки следует увеличить номер ее версии и доставить ее с помощью сборки политики издателя. В сборке политики издателя укажите, что новая вспомогательная сборка совместима с предыдущей версией. Диспетчер ресурсов будет использовать атрибут <xref:System.Resources.SatelliteContractVersionAttribute> , чтобы определить версию вспомогательной сборки, но загрузчик сборок будет привязан к версии вспомогательной сборки, указанной в политике издателя. Дополнительные сведения о сборках политик издателей см. в разделе [Создание файла политики издателя](../configure-apps/how-to-create-a-publisher-policy.md).  
  
 Чтобы включить полную поддержку управления версиями сборок, рекомендуется развернуть сборки со строгими именами в [глобальном кэше сборок](../app-domains/gac.md) , а сборки без строгих имен — в каталоге приложения. Если вы хотите развернуть сборки со строгими именами в каталоге приложения, то при обновлении сборки не сможете увеличить номер версии для вспомогательной сборки. Вместо этого необходимо выполнить обновление на месте, при котором вы заменяете существующий код обновленным, сохраняя тот же номер версии. Например, если вы хотите обновить версию 1.0.0.0 вспомогательной сборки с полностью заданным именем "myApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a", перезапишите ее обновленным файлом myApp.resources.dll, скомпилированным с использованием того же полностью заданного имени сборки "myApp.resources, Version=1.0.0.0, Culture=de, PublicKeyToken=b03f5f11d50a3a". Обратите внимание, что использование обновления на месте для файлов вспомогательных сборок затрудняет приложению задачу по корректному определению версии вспомогательной сборки.  
  
 Дополнительные сведения об управлении версиями сборок см. в разделах [Управление версиями сборок](../../standard/assembly/versioning.md) и [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).  
  
<a name="from_file"></a>   
## <a name="retrieving-resources-from-resources-files"></a>Извлечение ресурсов из файлов RESOURCES  
 Если вы решили не развертывать ресурсы в вспомогательных сборках, то все равно можете воспользоваться объектом <xref:System.Resources.ResourceManager> для прямого доступа к ресурсам из файлов RESOURCES. Для этого требуется развернуть файлы RESOURCES правильным образом. После этого используйте метод <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%2A?displayProperty=nameWithType> для создания экземпляра объекта <xref:System.Resources.ResourceManager> и укажите каталог, содержащий автономные файлы RESOURCES.  
  
### <a name="deploying-resources-files"></a>Развертывание файлов RESOURCES  
 При внедрении файлов RESOURCES в сборку приложения и вспомогательные сборки все вспомогательные сборки имеют одинаковое имя файла, однако каждая из них помещается в подкаталог, который отражает ее язык и региональные параметры. И наоборот, при прямом доступе к ресурсам из RESOURCES-файлов все эти файлы можно поместить в один каталог, который обычно находится в каталоге приложения. Имя RESOURCES-файла по умолчанию для приложения состоит только из корневого имени без указания языка и региональных параметров (например, strings.resources). Ресурсы для каждого локализованного языка хранятся в файле, имя которого состоит из корневого имени, за которым следует обозначение языка и региональных параметров (например, strings.ja.resources или strings.de DE.resources). 
 
 На следующем рисунке показано, где должны находиться файлы ресурсов в структуре каталогов. На нем также приведены соглашения об именовании для файлов RESOURCE.  

 ![Рисунок, показывающий главную папку приложения.](./media/retrieving-resources-in-desktop-apps/resource-application-directory.gif)  
  
### <a name="using-the-resource-manager"></a>Использование диспетчера ресурсов  
 После создания ресурсов и помещения их в соответствующий каталог создайте объект <xref:System.Resources.ResourceManager> , чтобы использовать ресурсы путем вызова метода <xref:System.Resources.ResourceManager.CreateFileBasedResourceManager%28System.String%2CSystem.String%2CSystem.Type%29> . Первый параметр указывает корневое имя RESOURCES-файла по умолчанию в приложении (в примере из предыдущего раздела этому соответствует "strings"). Второй параметр указывает расположение ресурсов ("Resources" в предыдущем примере). Третий параметр указывает используемую реализацию <xref:System.Resources.ResourceSet> . Если третий параметр равен `null`, используется среда выполнения по умолчанию <xref:System.Resources.ResourceSet> .  
  
> [!NOTE]
> Не развертывайте приложения ASP.NET с использованием автономных файлов RESOURCES. Это может привести к проблемам с блокировкой и нарушениям развертывания XCOPY. Рекомендуется развертывать ресурсы ASP.NET во вспомогательных сборках. Дополнительные сведения см. в разделе [ASP.NET Web Page Resources Overview](https://docs.microsoft.com/previous-versions/aspnet/ms227427(v=vs.100)).  
  
 После его создания экземпляра объекта <xref:System.Resources.ResourceManager> используйте методы <xref:System.Resources.ResourceManager.GetString%2A>, <xref:System.Resources.ResourceManager.GetObject%2A>и <xref:System.Resources.ResourceManager.GetStream%2A> для извлечения ресурсов, как было описано выше. Однако получение ресурсов непосредственно из RESOURCES-файлов отличается от извлечения внедренных ресурсов из сборок. При получении ресурсов из RESOURCES-файлов методы <xref:System.Resources.ResourceManager.GetString%28System.String%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%29>и <xref:System.Resources.ResourceManager.GetStream%28System.String%29> всегда извлекают ресурсы для языка и региональных параметров по умолчанию, независимо от текущего их значения. Чтобы извлечь ресурсы для текущей или конкретной комбинации языка и региональных параметров приложения, необходимо вызвать метод <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>, <xref:System.Resources.ResourceManager.GetObject%28System.String%2CSystem.Globalization.CultureInfo%29>или <xref:System.Resources.ResourceManager.GetStream%28System.String%2CSystem.Globalization.CultureInfo%29> и указать комбинацию языка и региональных параметров, ресурсы которой требуется получить. Чтобы получить ресурсы для текущего языка и региональных параметров, укажите значение свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> в качестве аргумента `culture` . Если диспетчер ресурсов не может извлечь ресурсы `culture`, для извлечения необходимых ресурсов он использует стандартные правила резервных ресурсов.  
  
### <a name="an-example"></a>Пример  
 В следующем примере показано, как диспетчер ресурсов получает ресурсы непосредственно из RESOURCES-файлов. Пример состоит из трех текстовых файлов ресурсов для английского (США), французского (Франция) и русского (Россия) языков и соответствующих региональных параметров. В этом примере по умолчанию задан английский язык (США). Его ресурсы хранятся в файле с именем Strings.txt:  
  
```text
Greeting=Hello  
Prompt=What is your name?  
```  
  
 Ресурсы для французского языка (Франция) хранятся в следующем файле с именем Strings.fr-FR.txt:  
  
```text 
Greeting=Bon jour  
Prompt=Comment vous appelez-vous?  
```  
  
 Ресурсы для русского языка (Россия) хранятся в следующем файле с именем Strings.ru-RU.txt:  
  
```text
Greeting=Здравствуйте  
Prompt=Как вас зовут?  
```  
  
 Ниже приведен исходный код для этого примера. В примере создаются экземпляры объектов <xref:System.Globalization.CultureInfo> для английского языка (США), английского языка (Канада), французского языка (Франция) и русского языка (Россия), и каждый из этих языков делается текущим. Метод <xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> передает значение свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> в виде аргумента `culture` для извлечения подходящих ресурсов для конкретного языка и региональных параметров.  
  
 [!code-csharp[Conceptual.Resources.Retrieving#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.retrieving/cs/example3.cs#9)]
 [!code-vb[Conceptual.Resources.Retrieving#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.retrieving/vb/example3.vb#9)]  
  
 Версию примера на языке C# можно скомпилировать, запустив следующий пакетный файл. Если используется Visual Basic, замените `csc` на `vbc`и расширение `.cs` на `.vb`.  
  
```console
Md Resources  
Resgen Strings.txt Resources\Strings.resources  
Resgen Strings.fr-FR.txt Resources\Strings.fr-FR.resources  
Resgen Strings.ru-RU.txt Resources\Strings.ru-RU.resources  
  
csc Example.cs  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Resources.ResourceManager>
- [Ресурсы в приложениях для настольных систем](index.md)
- [Упаковка и развертывание ресурсов](packaging-and-deploying-resources-in-desktop-apps.md)
- [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md)
- [Создание и извлечение ресурсов в приложениях для Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/hh694557(v=vs.140))
