---
title: Элемент <providerOption>
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 9c69ea7bf95b311a796ec29d90410a77b748c3c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229788"
---
# <a name="provideroption-element"></a>\<providerOption > элемент
Задает атрибуты версии компилятора для поставщика языка.  
  
 \<Элемент Configuration >  
\<system.codedom Element>  
\<Элемент compilers >  
\<Компилятор > элемент  
\<providerOption > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Задает имя параметра; Например, «CompilerVersion».|  
|`value`|Обязательный атрибут.<br /><br /> Указывает значение для параметра; Например «v3.5».|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|  
|[\<System.CodeDom > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[\<компиляторы > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.|  
|[Элемент \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 3.5, поставщики код объектной модели документов кода (CodeDOM) могут поддерживать параметры поставщика с помощью `<providerOption>` элемент.  
  
 .NET Framework 3.5, включает обновленные сборки .NET Framework 2.0 и предоставляет новые сборки версии 3.5, которые содержат новые типы. Поставщики кода Microsoft C# и Visual Basic, находятся в сборках .NET Framework 2.0, но были обновлены для поддержки компиляторы версии 3.5. По умолчанию поставщики обновленный код создания кода для компиляторов версии 2.0. Можно использовать `<providerOption>` элемент для изменения целевой версии компилятора 3.5. Чтобы сделать это, укажите «Версию компилятора» для `name` атрибут и «v3.5» для `value` атрибута. Должен предшествовать номер версии с прописной буквы «v».  
  
 Спецификация версии можно сделать глобальным путем добавления `<providerOption>` элемент в .NET Framework 2.0 Machine.config или корневом файле Web.config. Если вы не обновите версию компилятора по умолчанию 3.5 в файле Machine.config, можно изменить его обратно в 2.0 на основе каждого приложения с помощью `<providerOption>` элемент в файле конфигурации приложения.  
  
 Реализации поставщика кода codeDOM может обрабатывать настраиваемых параметров, предоставляя конструктор, принимающий `providerOptions` параметр типа <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как указать, следует использовать поставщика кода C# версии 3.5.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<компиляторы > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Элемент Compiler для компиляторов для compilation (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
