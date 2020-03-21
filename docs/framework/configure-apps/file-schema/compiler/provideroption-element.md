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
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155405"
---
# <a name="provideroption-element"></a>\<providerOption> Элемент
Определяет атрибуты версии компилятора для поставщика языковых данных.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>составители**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<компилятор>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

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
  
|attribute|Описание|  
|---------------|-----------------|  
|`name`|Обязательный атрибут.<br /><br /> Упогоняет название опции; например, "CompilerVersion".|  
|`value`|Обязательный атрибут.<br /><br /> Упогоняет значение опциона; например, "v3.5".|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<конфигурация> Элемент](../configuration-element.md)|Корневой элемент в любом файле конфигурации, который используется средой CLR и приложениями .NET Framework.|  
|[\<system.codedom> Элемент](system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[\<компиляторы> Элемент](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль `<compiler>` или более элементов.|  
|[\<компилятор> Элемент](compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
## <a name="remarks"></a>Remarks  
 В версии .NET Framework 3.5 поставщики кода-объекта документа (CodeDOM) могут `<providerOption>` поддерживать определенные параметры поставщика с помощью элемента.  
  
 Рамочный 3.net Framework 3.5 включает в себя обновленные сборки .NET Framework 2.0 и предоставляет новую версию 3.5 сборок, содержащих новые типы. Поставщики кода Microsoft C и Visual Basic содержатся в сборках .NET Framework 2.0, но были обновлены для поддержки компиляторов версии 3.5. По умолчанию поставщики обновленного кода генерируют код для компиляторов версии 2.0. Элемент можно `<providerOption>` использовать для изменения целевой версии компилятора до 3.5. Для этого укажите "CompilerVersion" `name` для атрибута и "v3.5" для атрибута. `value` Вы должны предшествовать номеру версии с нижним случаем "v".  
  
 Вы можете сделать спецификацию `<providerOption>` версии глобальной, добавив элемент в .NET Framework 2.0 Machine.config или корневый файл Web.config. Если вы обновите версию компилятора по умолчанию до 3.5 в файле Machine.config, вы можете изменить ее обратно до 2.0 на основе в расчете на одну заявку, используя `<providerOption>` элемент в файле конфигурации приложения.  
  
 Исполнители код-провайдеров CodeDOM могут обрабатывать пользовательские `providerOptions` параметры, <xref:System.Collections.Generic.IDictionary%602>предоставляя конструктору, который принимает параметр типа.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что должна использоваться версия 3.5 поставщика кода С.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема конфигурации файлов](../index.md)
- [\<компиляторы> Элемент](compilers-element.md)
- [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Элемент compiler для элемента compilers для элемента compilation (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
