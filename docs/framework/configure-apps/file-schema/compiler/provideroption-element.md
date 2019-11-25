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
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088675"
---
# <a name="provideroption-element"></a>\<Провидероптион > элемент
Указывает атрибуты версии компилятора для поставщика языка.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. codedom >** ](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<компилятора**](compilers-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**компилятора**](compiler-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<провидероптион >**

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
|`name`|Обязательный атрибут.<br /><br /> Указывает имя параметра. Например, "Компилерверсион".|  
|`value`|Обязательный атрибут.<br /><br /> Задает значение для параметра; Например, "v 3.5".|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<configuration>](../configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|  
|[\<System. CodeDom > элемент](system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[\<компиляторы > элемент](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов `<compiler>`.|  
|[Элемент \<compiler>](compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
## <a name="remarks"></a>Заметки  
 В .NET Framework версии 3,5 поставщики кода Code Document Object Model (CodeDOM) могут поддерживать зависящие от поставщика параметры с помощью элемента `<providerOption>`.  
  
 .NET Framework 3,5 включает обновленные сборки .NET Framework 2,0 и предоставляет новые сборки версии 3,5, содержащие новые типы. Поставщики кода C# Microsoft и Visual Basic содержатся в сборках .NET Framework 2,0, но были обновлены для поддержки компиляторов версии 3,5. По умолчанию обновленные поставщики кода создают код для компиляторов версии 2,0. Можно использовать элемент `<providerOption>`, чтобы изменить целевую версию компилятора на 3,5. Для этого укажите "Компилерверсион" для атрибута `name` и "v 3.5" для атрибута `value`. Перед номером версии необходимо указать строчную букву "v".  
  
 Глобальную спецификацию версии можно сделать, добавив элемент `<providerOption>` в файл Web. config .NET Framework 2,0 Machine. config или root. Если вы обновляете версию компилятора по умолчанию до 3,5 в файле Machine. config, вы можете изменить ее обратно на 2,0 для каждого приложения, используя элемент `<providerOption>` в файле конфигурации приложения.  
  
 Разработчики поставщика кода CodeDOM могут обрабатывать пользовательские параметры, предоставляя конструктор, принимающий параметр `providerOptions` типа <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что должен использоваться поставщик C# кода версии 3,5.  
  
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
- [Схема файла конфигурации](../index.md)
- [\<компиляторы > элемент](compilers-element.md)
- [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Элемент компилятора для компиляторов для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
