---
title: Элемент <supportPortability>
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 011793006f2aff32486fbe4537b46517e0a2b888
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252306"
---
# <a name="supportportability-element"></a>\<Элемент > тег supportportability
Указывает, что приложение может ссылаться на ту же сборку в двух различных реализациях .NET Framework, отключая поведение по умолчанию, которое рассматривает сборки как эквивалент для переносимости приложения.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Тег supportportability >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  

В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|PKT|Обязательный атрибут.<br /><br /> Указывает токен открытого ключа для затронутой сборки в виде строки.|  
|enabled|Необязательный атрибут.<br /><br /> Указывает, должна ли быть включена поддержка переносимости между реализациями указанной .NET Framework сборки.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|true|Включить поддержку переносимости между реализациями указанной .NET Framework сборки. Это значение по умолчанию.|  
|false|Отключение поддержки переносимости между реализациями указанной .NET Framework сборки. Это позволяет приложению иметь ссылки на несколько реализаций указанной сборки.|  
  
### <a name="child-elements"></a>Дочерние элементы  

Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
  
## <a name="remarks"></a>Примечания  

Начиная с .NET Framework 4, поддержка предоставляется автоматически для приложений, которые могут использовать любую из двух реализаций .NET Framework, например либо реализацию .NET Framework, либо .NET Framework для реализации Silverlight. Две реализации конкретной .NET Framework сборки считаются эквивалентными связывателем сборки. В нескольких сценариях эта функция переносимости приложений вызывает проблемы. В этих сценариях `<supportPortability>` элемент можно использовать для отключения функции.  
  
Одним из таких сценариев является сборка, которая должна ссылаться как на реализацию .NET Framework, так и на .NET Framework для реализации в Silverlight конкретной ссылочной сборки. Например, конструктору XAML, написанному на Windows Presentation Foundation (WPF), может потребоваться ссылка на реализацию WPF настольной системы, для пользовательского интерфейса конструктора и подмножество WPF, включенное в реализацию Silverlight. По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки. Этот элемент отключает поведение по умолчанию и обеспечивает успешную компиляцию.  
  
> [!IMPORTANT]
> Чтобы компилятор мог передать информацию в логику привязки сборки среды CLR, необходимо использовать `/appconfig` параметр компилятора, чтобы указать расположение файла App. config, содержащего этот элемент.  
  
## <a name="example"></a>Пример  

В следующем примере приложение включает ссылки на реализацию .NET Framework и .NET Framework для реализации Silverlight любой .NET Framework сборки, которая существует в обеих реализациях. Для указания расположения этого файла App. config необходимо использовать параметр компилятора.`/appconfig`  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [/appconfig (C# параметры компилятора)](../../../../csharp/language-reference/compiler-options/appconfig-compiler-option.md)
- [Общие сведения об унификации сборок .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/db7849ey(v=vs.100))
