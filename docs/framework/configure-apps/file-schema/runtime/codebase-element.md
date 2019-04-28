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
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674198"
---
# <a name="codebase-element"></a>\<codeBase > элемент

Указывает, где среда CLR может найти сборку.

\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase>

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
|`href`|Обязательный атрибут.<br /><br /> Указывает URL-адрес, где среда выполнения может найти указанную версию сборки.|
|`version`|Обязательный атрибут.<br /><br /> Указывает версию сборки, к которым применяется базы кода. Формат номера версии сборки *major.minor.build.revision*.|

## <a name="version-attribute"></a>Атрибут версии

|Значение|Описание|
|-----------|-----------------|
|Допустимые значения для каждой части номера версии: от 0 до 65535.|Неприменимо.|

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|`buildproviders`|Определяет набор поставщиков построения, которые используются для компиляции пользовательских файлов ресурсов. Можно использовать любое число поставщиков построения.|
|`compilation`|Настраивает все параметры, используемые платформой ASP.NET.|
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|`System.web`|Задает корневой элемент для раздела конфигурации ASP.NET.|

## <a name="remarks"></a>Примечания

Для среды выполнения для использования  **\<codeBase >** параметр в файле конфигурации компьютера или файле политики издателя, файл должен также перенаправление версии сборки. Файлы конфигурации приложения может иметь параметр базы кода без перенаправления версии сборки. Выяснив, какие версии сборки, среда выполнения применяется параметр базы кода из файла, который определяет версию. Если база кода, среда выполняет поиск сборки обычным способом.

Если сборка имеет строгое имя, параметр базы кода может быть в любом месте в локальной интрасети или в Интернете. Если сборка является закрытой сборки, параметр базы кода должен быть путь относительно каталога приложения.

Для сборок без строгого имени, версия игнорируется, и загрузчик использует первое значение \<codebase > внутри \<dependentAssembly >. Если имеется запись в файле конфигурации приложения, перенаправление привязки в другую сборку, перенаправление будет иметь приоритет, даже если версия сборки не соответствует запросу.

## <a name="example"></a>Пример

Приведенный ниже показано, как указать, где среда выполнения может найти сборку.

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

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Указание расположения сборки](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
