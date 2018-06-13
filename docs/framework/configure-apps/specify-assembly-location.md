---
title: Указание сборки&#39;расположение s
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 65bd075115e33486e86e8081b01b96db665e9da5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758273"
---
# <a name="specifying-an-assembly39s-location"></a>Указание сборки&#39;расположение s
Указание расположения сборки двумя способами.  
  
-   С помощью [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) элемента.  
  
-   С помощью [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемента.  
  
 Можно также использовать [средства настройки .NET Framework (Mscorcfg.msc)](http://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) чтобы задавать расположение сборки или расположения для поиск сборок CLR.  
  
## <a name="using-the-codebase-element"></a>С помощью \<codeBase > элемент  
 Можно использовать  **\<codeBase >** элемент только в машине конфигурации или файле политики издателя, также предоставляют перенаправление версии сборки. Среда выполнения определяет, какие версии сборки для использования, применяется параметр базы кода из файла, который определяет версию. Если база кода не указана, среда выполнения проверяет наличие сборки обычным способом. Дополнительные сведения см. в разделе [как среда выполнения находит сборки](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 В следующем примере показано, как указание расположения сборки.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **Версии** атрибут является обязательным для всех сборок со строгими именами, но должен быть опущен для сборок, которые не имеют строгие имена. **\<CodeBase >** элемента требуется **href** атрибута. Нельзя определить диапазон версий в  **\<codeBase >** элемента.  
  
> [!NOTE]
>  Если вы указали подсказка базы кода для сборки, не имеет строгого имени, должна указывать базовой папки приложения или является подкаталогом базового каталога приложения.  
  
## <a name="using-the-probing-element"></a>С помощью \<probing > элемент  
 Среда выполнения ищет сборки, которые не имеют базы кода при проверке. Дополнительные сведения о поиске см. в разделе [как среда выполнения находит сборки](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Можно использовать [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) в файле конфигурации приложения для указания подкаталогов, среда выполнения должна использовать при определении расположения сборки. Приведенный ниже показано, как указать каталоги, в которых среда выполнения должна выполнять поиск.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **PrivatePath** атрибут содержит каталоги, которые среда выполнения будет выполняться поиск сборок. Если приложение находится в C:\Program Files\MyApp, среда выполнения ищет сборки, которые не указаны базы кода в C:\Program Files\MyApp\Bin C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3. Каталоги, заданные в **privatePath** должны быть подкаталогами базовой папки приложения.  
  
## <a name="see-also"></a>См. также  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Настройка приложений .NET Framework](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
