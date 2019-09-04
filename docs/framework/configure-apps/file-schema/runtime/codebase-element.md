---
title: Элемент <codeBase>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: bd170b817c5ccc337711f8f79968653c29f3eda4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252747"
---
# <a name="codebase-element"></a>\<Элемент codeBase >

Указывает, где среда CLR может найти сборку.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<База кода >**

## <a name="syntax"></a>Синтаксис

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|Атрибут|Описание|
|---------------|-----------------|
|`href`|Обязательный атрибут.<br /><br /> Указывает URL-адрес, по которому среда выполнения может найти указанную версию сборки.|
|`version`|Обязательный атрибут.<br /><br /> Указывает версию сборки, к которой применяется база кода. Номер версии сборки имеет формат *основной. дополнительный. сборка. Редакция*.|

## <a name="version-attribute"></a>Атрибут версии

|Значение|Описание|
|-----------|-----------------|
|Допустимые значения для каждой части номера версии — от 0 до 65535.|Не применяется|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`buildproviders`|Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов. Можно использовать любое число поставщиков построения.|
|`compilation`|Настраивает все параметры компиляции, используемые ASP.NET.|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`System.web`|Задает корневой элемент для раздела конфигурации ASP.NET.|

## <a name="remarks"></a>Примечания

Чтобы среда выполнения использовала  **\<параметр базы кода >** в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправлять версию сборки. Файлы конфигурации приложения могут иметь параметр базы кода без перенаправления версии сборки. После определения используемой версии сборки среда выполнения применяет параметр базы кода из файла, определяющего версию. Если база кода не указана, среда выполнения проверяет наличие сборки обычным способом.

Если сборка имеет строгое имя, параметр базы кода может находиться в любом месте локальной интрасети или в Интернете. Если сборка является закрытой, параметр базы кода должен быть путем относительно каталога приложения.

Для сборок без строгого имени версия игнорируется, а загрузчик использует первый внешний вид \<базы кода > в \<dependentAssembly >. Если в файле конфигурации приложения имеется запись, которая перенаправляет привязку к другой сборке, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу привязки.

## <a name="example"></a>Пример

В следующем примере показано, как указать, где среда выполнения может найти сборку.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Указание расположения сборки](../../specify-assembly-location.md)
- [Обнаружение сборок в среде выполнения](../../../deployment/how-the-runtime-locates-assemblies.md)
