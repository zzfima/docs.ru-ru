---
title: Работа с RESX-файлами программным способом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resource files, .resx files
- .resx files
ms.assetid: 168f941a-2b84-43f8-933f-cf4a8548d824
ms.openlocfilehash: 2bbca5712639e14370d090e95b78bb89eba134e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129910"
---
# <a name="working-with-resx-files-programmatically"></a>Работа с RESX-файлами программным способом
Поскольку XML-файлы ресурсов (RESX-файлы) должны иметь четко определенный XML-формат (включая заголовок, который должен соответствовать конкретной схеме и за которым следуют данные в парах "имя-значение"), создание этих файлов вручную может приводить к ошибкам. RESX-файлы можно также создавать программным способом, используя типы и члены из библиотеки классов .NET. Кроме того, библиотеку классов .NET можно использовать для извлечения ресурсов, хранящихся в RESX-файлах. В этой статье рассматривается использование типов и членов из пространства имен <xref:System.Resources> для работы с RESX-файлами.

 Обратите внимание, что здесь рассматривается работа с XML-файлами (RESX-файлами), содержащими ресурсы. Сведения о работе с двоичными файлами ресурсов, внедренными в сборки, см. в статье <xref:System.Resources.ResourceManager> .

> [!WARNING]
> Существуют также способы работы с RESX-файлами, отличные от программных. При добавлении в проект [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) файла ресурсов среда Visual Studio предоставляет интерфейс для создания и обслуживания RESX-файла и во время компиляции автоматически преобразует RESX-файл в RESOURCES-файл. Для непосредственной работы с RESX-файлом можно также использовать текстовый редактор. Однако следует соблюдать осторожность и избегать изменения содержащихся в файле двоичных данных: это может привести к его повреждению.

## <a name="create-a-resx-file"></a>Создание RESX-файла

Для создания RESX-файла программным способом можно использовать класс <xref:System.Resources.ResXResourceWriter?displayProperty=nameWithType> , выполнив следующие действия.

1. Создайте экземпляр объекта <xref:System.Resources.ResXResourceWriter> , вызвав метод <xref:System.Resources.ResXResourceWriter.%23ctor%28System.String%29?displayProperty=nameWithType> и указав имя RESX-файла. Имя файла должно включать в себя расширение RESX. Если экземпляр объекта <xref:System.Resources.ResXResourceWriter> создается в блоке `using` , явный вызов метода <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> на шаге 3 не требуется.

2. Вызовите метод <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> для каждого ресурса, который необходимо добавить в файл. Используйте перегрузки этого метода для добавления строки, объекта и двоичных данных (массива байтов). Если ресурсом является объект, он должен быть сериализуемым.

3. Вызовите метод <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> для создания файла ресурсов и освобождения всех ресурсов. Если объект <xref:System.Resources.ResXResourceWriter> был создан в блоке `using` , ресурсы записываются в RESX-файл, а ресурсы, используемые объектом <xref:System.Resources.ResXResourceWriter> , освобождаются в конце блока `using` .

В полученном RESX-файле имеется соответствующий заголовок и тег `data` для каждого ресурса, добавленного методом <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> .

> [!WARNING]
> Не следует использовать файлы ресурсов для хранения паролей, конфиденциальной информации или личных данных.

В следующем примере создается RESX-файл с именем CarResources.resx, в котором хранятся шесть строк, значок и два объекта, определяемых приложением (два объекта `Automobile` ). Обратите внимание, что класс `Automobile`, определенный и созданный в этом примере, отмечен атрибутом <xref:System.SerializableAttribute>.

[!code-csharp[Conceptual.Resources.ResX#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/create1.cs#1)]
[!code-vb[Conceptual.Resources.ResX#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/create1.vb#1)]

> [!TIP]
> Для создания RESX-файлов можно также использовать [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Во время компиляции Visual Studio использует [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) для преобразования RESX-файла в двоичный файл ресурсов (RESOURCES-файл) и внедряет этот файл в сборку приложения или вспомогательную сборку.

RESX-файл нельзя внедрить в исполняемый файл или скомпилировать во вспомогательную сборку. Необходимо преобразовать RESX-файл в двоичный файл ресурсов (RESOURCES-файл) с помощью [генератора файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md). Затем полученный RESOURCES-файл можно внедрить в сборку приложения или вспомогательную сборку. Дополнительные сведения см. в разделе [Creating Resource Files](creating-resource-files-for-desktop-apps.md).

## <a name="enumerate-resources"></a>Перечисление ресурсов
 В некоторых случаях может потребоваться извлечь из RESX-файла все ресурсы, а не конкретный ресурс. Для этого можно использовать класс <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> , предоставляющий перечислитель для всех ресурсов в RESX-файле. Класс <xref:System.Resources.ResXResourceReader?displayProperty=nameWithType> реализует перечислитель <xref:System.Collections.IDictionaryEnumerator>, который возвращает объект <xref:System.Collections.DictionaryEntry> , представляющий конкретный ресурс для каждой итерации цикла. Его свойство <xref:System.Collections.DictionaryEntry.Key%2A?displayProperty=nameWithType> возвращает ключ ресурса, а свойство <xref:System.Collections.DictionaryEntry.Value%2A?displayProperty=nameWithType> — значение ресурса.

 В следующем примере создается объект <xref:System.Resources.ResXResourceReader> для файла CarResources.resx, созданного в предыдущем примере, а затем выполняются итерации по файлу ресурсов. В этом примере в объект `Automobile` добавляются два объекта <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> , определенные в файле ресурсов, а в объект <xref:System.Collections.SortedList> добавляются пять строк из шести. Значения в объекте <xref:System.Collections.SortedList> преобразуются в массив параметров, который используется для отображения заголовков столбцов в консоли. Значения свойства `Automobile` также выводятся на консоль.

 [!code-csharp[Conceptual.Resources.ResX#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/enumerate1.cs#2)]
 [!code-vb[Conceptual.Resources.ResX#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/enumerate1.vb#2)]

## <a name="retrieve-a-specific-resource"></a>Получение определенного ресурса
 Помимо перечисления элементов в RESX-файле, можно извлечь конкретный ресурс по имени, используя класс <xref:System.Resources.ResXResourceSet?displayProperty=nameWithType> . Метод <xref:System.Resources.ResourceSet.GetString%28System.String%29?displayProperty=nameWithType> извлекает значение именованного строкового ресурса. Метод <xref:System.Resources.ResourceSet.GetObject%28System.String%29?displayProperty=nameWithType> извлекает значение именованного объекта или двоичные данные. Этот метод возвращает объект, который затем должен быть приведен (в C#) или преобразован (в Visual Basic) в объект нужного типа.

 В следующем примере извлекается строка заголовка и значок формы по именам ресурсов. В нем также извлекаются определяемые приложением объекты `Automobile`, использованные в предыдущем примере, и эти объекты отображаются в элементе управления <xref:System.Windows.Forms.DataGridView>.

 [!code-csharp[Conceptual.Resources.ResX#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resx/cs/retrieve1.cs#3)]
 [!code-vb[Conceptual.Resources.ResX#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resx/vb/retrieve1.vb#3)]

## <a name="convert-resx-files-to-binary-resources-files"></a>Преобразование RESX-файлов в двоичные RESOURCES-файлы
 Преобразование RESX-файлов во внедряемые двоичные файлы ресурсов (RESOURCES-файлы) имеет значительные преимущества. Хотя RESX-файлы легко читаются и обслуживаются при развертывании приложения, они редко поставляются с готовыми приложениями. Если они распространяются с приложением, то существуют в виде отдельных файлов наряду с исполняемым файлом приложения и сопровождающими его библиотеками. В отличие от RESX-файлов RESOURCES-файлы внедряются в исполняемый файл приложения или сопровождающие его сборки. Кроме того, если локализованные приложения полагаются на RESX-файлы во время выполнения, это означает, что ответственность за обработку перехода к другим ресурсам несет разработчик. Напротив, если создан ряд вспомогательных сборок, содержащих внедренные RESOURCES-файлы, процесс перехода на резервные ресурсы обрабатывается средой CLR.

 Для преобразования RESX-файла в RESOURCES-файл используется [генератор файлов ресурсов (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md), который имеет следующий базовый синтаксис:

 **Resgen.exe** *имя_RESX_файла*

 Результат — двоичный файл ресурсов, который имеет такое же корневое имя файла, что и RESX-файл, и расширение RESOURCES-файла. Затем во время компиляции этот файл может быть компилирован в исполняемый файл или библиотеку. Если применяется компилятор Visual Basic, для внедрения RESOURCES-файла в исполняемый файл приложения используйте следующий синтаксис:

 **vbc** *filename* **.vb -resource:** *.resourcesFilename*

 При использовании C# синтаксис следующий:

 **csc** *filename* **.cs -resource:** *.resourcesFilename*

 Затем RESOURCES-файл может быть также внедрен во вспомогательную сборку с помощью [компоновщика сборок (AL.exe)](../tools/al-exe-assembly-linker.md), который имеет следующий базовый синтаксис:

 **al** *resourcesFilename* **-out:** *assemblyFilename*

## <a name="see-also"></a>См. также

- [Создание файлов ресурсов](creating-resource-files-for-desktop-apps.md)
- [Resgen.exe (генератор файлов ресурсов)](../tools/resgen-exe-resource-file-generator.md)
- [Al.exe (компоновщик сборок)](../tools/al-exe-assembly-linker.md)
