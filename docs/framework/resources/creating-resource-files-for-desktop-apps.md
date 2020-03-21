---
title: Создание файлов ресурсов для приложений .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resources files
- .resources files
- application resources, creating files
- resource files, creating
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
ms.openlocfilehash: b679539be1aeb593124eb35a235bcc578decb4c0
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111781"
---
# <a name="create-resource-files-for-net-apps"></a>Создание файлов ресурсов для приложений .NET

Ресурсы, такие как строки, изображения или данные объектов, можно включать в файлы ресурсов, чтобы сделать их легко доступными для приложения. В платформе .NET Framework предлагается пять способов создания файлов ресурсов.

- Создайте текстовый файл, содержащий строковые ресурсы. Для преобразования текстового файла в двоичный файл ресурсов (RESOURCES-файл) можно использовать [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Затем можно вставить файл двоичного ресурса в исполняемую заявку или библиотеку приложений с помощью компилятора языка, или вы можете вставить его в спутниковую сборку с помощью [Ассамблеи Linker (Al.exe).](../tools/al-exe-assembly-linker.md) Дополнительные сведения см. в разделе [Ресурсы в текстовых файлах](creating-resource-files-for-desktop-apps.md#TextFiles).

- Создайте XML-файл ресурсов (RESX-файл), который содержит строки, изображения или данные объектов. Для преобразования RESX-файла в двоичный файл ресурсов (RESOURCES-файл) можно использовать [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Затем двоичный файл ресурсов можно внедрить в исполняемый файл приложения или библиотеку приложения с помощью компилятора языка или во вспомогательную сборку с помощью [компоновщика сборок (Al.exe)](../tools/al-exe-assembly-linker.md). Дополнительные сведения см. в разделе [Ресурсы в RESX-файлах](creating-resource-files-for-desktop-apps.md#ResxFiles).

- Создайте XML-файл ресурсов (RESX-файл) программным способом с помощью типов в пространстве имен <xref:System.Resources>. Можно создать RESX-файл, перечислить его ресурсы и извлечь конкретные ресурсы по имени. Дополнительные сведения см. в разделе [Работа с RESX-файлами программным способом](working-with-resx-files-programmatically.md).

- Создайте двоичный файл ресурсов (RESOURCES-файл) программным способом. Затем этот файл можно внедрить в исполняемый файл приложения или библиотеку приложения с помощью компилятора языка или во вспомогательную сборку с помощью [компоновщика сборок (Al.exe)](../tools/al-exe-assembly-linker.md). Дополнительные сведения см. в разделе [Ресурсы в RESOURCES-файлах](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

- Создайте файл ресурсов в [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) и включите этот файл в проект. В Visual Studio есть редактор ресурсов,с помощью которого можно добавлять, удалять и изменять ресурсы. Во время компиляции файл ресурсов автоматически преобразуется в двоичный RESOURCES-файл и внедряется в сборку приложения или вспомогательную сборку. Дополнительные сведения см. в разделе [Файлы ресурсов в Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles).

<a name="TextFiles"></a>
## <a name="resources-in-text-files"></a>Ресурсы в формате текстовых файлов

В текстовых файлах (TXT или RESTEXT) можно сохранять только строковые ресурсы. Для нестроковых ресурсов используйте RESX-файлы или создавайте их программными средствами. Текстовые файлы, содержащие строковые ресурсы, имеют следующий формат.

```text
# This is an optional comment.
name = value

; This is another optional comment.
name = value

; The following supports conditional compilation if X is defined.
#ifdef X
name1=value1
name2=value2
#endif

# The following supports conditional compilation if Y is undefined.
#if !Y
name1=value1
name2=value2
#endif
```

 Форматы TXT- и RESTEXT-файлов ресурсов идентичны. Расширение файла RESTEX служит для того, чтобы текстовые файлы сразу опознавались как файлы ресурсов на основе текста.

 Строковые ресурсы представляются в виде пар *имя/значение*, где *имя* — строка, определяющая ресурс, а *значение* — строка ресурса, которая возвращается при передаче *имени* методу извлечения ресурсов, например, <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>. *Имя* и *значение* должны быть разделены знаком равенства (=). Пример:

```text
FileMenuName=File
EditMenuName=Edit
ViewMenuName=View
HelpMenuName=Help
```

> [!CAUTION]
> Не следует использовать файлы ресурсов для хранения паролей, конфиденциальной информации или личных данных.

 В текстовых файлах допускаются пустые строки (то есть, ресурсы, значение которых равно <xref:System.String.Empty?displayProperty=nameWithType>). Пример:

```text
EmptyString=
```

 Начиная с .NET Framework 4.5 и во всех версиях .NET `#ifdef`Core, текстовые файлы поддерживают условную компиляцию с *символом*... `#endif` и `#if !` *символ*... `#endif` конструкций. Для определения символов можно использовать [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) с параметром `/define`. Каждый ресурс `#ifdef`требует своего *символа*... `#endif` или `#if !` *символ*... `#endif` построить. Если при использовании оператора `#ifdef` указан *символ*, связанный ресурс добавляется в RESOURCES-файл; в противном случае он не добавляется. Если при использовании оператора `#if !`*символ* не указан, связанный ресурс добавляется в RESOURCES-файл; в противном случае он не добавляется.

 Комментарии в текстовых файлах необязательны и начинаются с точки с запятой (;) или знака решетки (#) в начале строки. Строки с комментариями могут находиться в любом месте файла. Комментарии не включаются в скомпилированный RESOURCES-файл, созданный с помощью [генератора файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md).

 Любые пустые строки в текстовых файлах считаются содержащими пробелы и игнорируются.

 В следующем примере определяются два строковых ресурса с именами `OKButton` и `CancelButton`.

```text
#Define resources for buttons in the user interface.
OKButton=OK
CancelButton=Cancel
```

 Если в текстовом файле содержатся дубликаты *имен*, [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) отображает предупреждение и игнорирует второе имя.

 *значение* не может содержать новые символы строки, но вы `\n` можете использовать C `\t` язык стиле побега символов, таких как представлять новую строку и представлять вкладку. Вы также можете включить backslash характер, если он\\\\сбежал (например, ""). Также допускаются пустые строки.

 Сохранить ресурсы в формате текстовых файлов с помощью кодирования UTF-8 или кодирования UTF-16 в порядке малого конца или большого конца. Но [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), преобразующий TXT-файл в RESOURCES-файл, по умолчанию обрабатывает файлы в кодировке UTF-8. Если вы хотите, чтобы программа Resgen.exe могла работать с файлом в кодировке UTF-16, необходимо указать метку порядка байтов Юникода (U+FEFF) в начале файла.

 Чтобы внедрить файл ресурсов в текстовом формате в сборку .NET, необходимо преобразовать текстовый файл в двоичный файл ресурсов (RESOURCES) с помощью [генератора файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Затем можно внедрить RESOURCES-файл в сборку .NET с помощью компилятора языка или во вспомогательную сборку с помощью [компоновщика сборок (Al.exe)](../tools/al-exe-assembly-linker.md).

 В следующем примере используется файл ресурсов в текстовом формате GreetingResources.txt для простого консольного приложения "Hello World". Текстовый файл определяет две `prompt` строки, и, `greeting`что побудить пользователя ввести свое имя и отобразить приветствие.

```text
# GreetingResources.txt
# A resource file in text format for a "Hello World" application.
#
# Initial prompt to the user.
prompt=Enter your name:
# Format string to display the result.
greeting=Hello, {0}!
```

Текстовый файл преобразуется в RESOURCES-файл с помощью следующей команды:

```console
resgen GreetingResources.txt
```

 В следующем примере показан исходный код для консольного приложения, которое получает сообщения из RESOURCES-файла и выводит их на экран.

 [!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)]
 [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]

 Если вы используете Visual Basic и файл с исходным кодом называется Greeting.vb, используйте следующую команду для создания исполняемого файла, содержащего внедренный RESOURCES-файл:

```console
vbc greeting.vb -resource:GreetingResources.resources
```

 Если вы используете C# и файл исходного кода называется Greeting.cs, исполняемый файл, содержащий внедренный RESOURCES-файл, создается с помощью следующей команды:

```console
csc greeting.cs -resource:GreetingResources.resources
```

<a name="ResxFiles"></a>
## <a name="resources-in-resx-files"></a>Ресурсы в RESX-файлах
 В отличие от текстовых файлов, в которых могут храниться только строковые ресурсы, в XML-файлах ресурсов (RESX) могут храниться строки, двоичные данные (такие как изображения, значки и аудиоклипы) и программные объекты. RESX-файл содержит стандартный заголовок, который описывает формат записей ресурсов и включает сведения о версии XML, которые используются для анализа данных. За заголовком XML следуют данные в файле ресурсов. Каждый элемент данных состоит из пары "имя-значение", заключенной в тег `data`. Атрибут `name` этого тега определяет имя ресурса, а вложенный тег `value` содержит значение ресурса. Для строковых данных тег `value` содержит строку.

 Например, следующий тег `data` определяет строковый ресурс с именем `prompt` и значением "Enter your name:".

```xml
<data name="prompt" xml:space="preserve">
  <value>Enter your name:</value>
</data>
```

> [!WARNING]
> Не следует использовать файлы ресурсов для хранения паролей, конфиденциальной информации или личных данных.

 Для объектов ресурсов тег **data** содержит атрибут `type`, указывающий тип данных ресурса. Для объектов, состоящих из двоичных данных, тег `data` также включает атрибут `mimetype`, который указывает тип `base64` двоичных данных.

> [!NOTE]
> Во всех RESX-файлах для создания и анализа двоичных данных заданного типа используется форматтер двоичной сериализации. В результате, если формат двоичной сериализации для объекта изменится недопустимым образом, RESX-файл может стать недействительным.

 В следующем примере показана часть RESX-файла, в которой содержится ресурс <xref:System.Int32> и растровое изображение.

```xml
<data name="i1" type="System.Int32, mscorlib">
  <value>20</value>
</data>

<data name="flag" type="System.Drawing.Bitmap, System.Drawing,
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"
    mimetype="application/x-microsoft.net.object.bytearray.base64">
  <value>
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…
  </value>
</data>
```

> [!IMPORTANT]
> Так как RESX-файлы должны представлять собой XML-код с правильным, заранее определенным форматом, с ними не рекомендуется работать вручную, особенно если они содержат нестроковые ресурсы. Вместо этого в [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) предусмотрен прозрачный интерфейс для создания RESX-файлов и управления ими. Дополнительные сведения см. в разделе [Файлы ресурсов в Visual Studio](creating-resource-files-for-desktop-apps.md#VSResFiles). Создавать RESX-файлы и управлять ими можно также программно. Дополнительные сведения см. в разделе [Работа с RESX-файлами программным способом](working-with-resx-files-programmatically.md).

<a name="ResourcesFiles"></a>
## <a name="resources-in-resources-files"></a>Ресурсы в RESOURCES-файлах

Для программного создания двоичного файла ресурсов (RESOURCES-файла) непосредственно из кода можно использовать класс <xref:System.Resources.ResourceWriter?displayProperty=nameWithType>. Для создания RESOURCES-файла из текстового файла или RESX-файла можно также использовать [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Помимо строковых данных, RESOURCES-файл может содержать двоичные данные (массивы байтов) и данные объектов. Для программного создания RESOURCES-файла необходимо выполнить следующие действия.

1. Создайте объект <xref:System.Resources.ResourceWriter> с уникальным именем файла. Это можно сделать, указав имя файла или файловый поток для конструктора класса <xref:System.Resources.ResourceWriter>.

2. Вызовите одну из перегрузок метода <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=nameWithType> для каждого именованного ресурса, который требуется добавить в файл. Ресурсом может быть строка, объект или коллекция двоичных данных (массив байтов).

3. Вызовете метод <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=nameWithType>, чтобы записать ресурсы в файл и закрыть объект <xref:System.Resources.ResourceWriter>.

> [!NOTE]
> Не следует использовать файлы ресурсов для хранения паролей, конфиденциальной информации или личных данных.

 В следующем примере программным способом создается RESOURCES-файл с именем CarResources.resources, в котором хранятся шесть строк, значок и два объекта, определяемые приложением (два объекта `Automobile`). Класс, `Automobile` который определен и мгновенно в примере, помечен <xref:System.SerializableAttribute> атрибутом, который позволяет ему сохраняться в бинарном размере сериализации.

 [!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)]
 [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]

 После создания RESOURCES-файла его можно внедрить в исполняемый файл среды выполнения или библиотеку, используя параметр `/resource` компилятора языка, или во вспомогательную сборку с помощью [компоновщик сборок (Al.exe)](../tools/al-exe-assembly-linker.md).

<a name="VSResFiles"></a>
## <a name="resource-files-in-visual-studio"></a>Файлы ресурсов в Visual Studio

При добавлении файла ресурсов в проект [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) среда Visual Studio создает RESX-файл в каталоге проекта. В Visual Studio имеются редакторы ресурсов, позволяющие добавлять строки, изображения и двоичные объекты. Так как редакторы предназначены для обработки только статических данных, их нельзя использовать для хранения программных объектов; данные объектов необходимо записывать в RESX- или RESOURCES-файл программным способом. Дополнительные сведения см. в статье [Работа с RESX-файлами программным способом](working-with-resx-files-programmatically.md) и разделе [Ресурсы в RESOURCES-файлах](creating-resource-files-for-desktop-apps.md#ResourcesFiles).

При добавлении локализованных ресурсов указывайте для них то же имя корневого файла, что и для основного файла ресурсов. Также в имени файла необходимо указать язык и региональные параметры. Например, при добавлении файла ресурсов с именем Resources.resx можно также создать файлы ресурсов с именами Resources.en-US.resx и Resources.fr-FR.resx, чтобы сохранить локализованные ресурсы для английского (США) и французского (Франция) языков и региональных параметров соответственно. Следует также указать язык и региональные параметры по умолчанию для приложения. Это язык и региональные параметры, ресурсы которых используются в том случае, если для конкретного языка и региональных параметров никаких локализованных ресурсов обнаружить не удается. Чтобы задать язык и региональные параметры по умолчанию, в обозревателе решений Visual Studio щелкните правой кнопкой мыши имя проекта, выберите "Приложение", щелкните **Сведения о сборке** и в списке **Нейтральный язык** выберите соответствующий язык и региональные параметры.

Во время компиляции среда Visual Studio сначала преобразует RESX-файлы проекта в двоичные файлы ресурсов (RESOURCES) и сохраняет их в подкаталоге каталога *obj* проекта. Visual Studio внедряет любые файлы ресурсов, не содержащие локализованные ресурсы, в основную сборку, созданную проектом. Если в каких-либо файлах ресурсов есть локализованные ресурсы, Visual Studio внедряет их в отдельные вспомогательные сборки для каждого локализованного языка и региональных параметров. Затем Visual Studio сохраняет каждую вспомогательную сборку в каталоге, имя которого соответствует локализованному языку и региональным параметрам. Например, локализованные ресурсы английского языка (США) сохраняются во вспомогательной сборке в подкаталоге en-US.

## <a name="see-also"></a>См. также раздел

- <xref:System.Resources>
- [Ресурсы в приложениях для настольных систем](index.md)
- [Packaging and Deploying Resources](packaging-and-deploying-resources-in-desktop-apps.md)
