---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 1bfa0ddbeba7546044a0d1ed15f4c2ff303b1491
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583632"
---
# <a name="specifying-an-assemblys-location"></a>Указание расположения сборки
Указание расположения сборки двумя способами:  
  
- С помощью [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) элемент.  
  
- С помощью [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент.  
  
 Можно также использовать [средством настройки .NET Framework (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) чтобы задавать расположение сборки или расположения для среда поиск сборок.  
  
## <a name="using-the-codebase-element"></a>С помощью \<codeBase > элемент  
 Можно использовать  **\<codeBase >** элемент только в машине конфигурации или файле политики издателя, которые также предоставляют перенаправление версии сборки. Среда выполнения определяет, какие версии сборки, применяется параметр базы кода из файла, который определяет версию. Если база кода не указана, среда выполняет поиск сборки обычным способом. Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
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
  
 **Версии** атрибут является обязательным для всех сборок со строгими именами, но должен быть опущен для сборок, которые не имеют строгие имена.  **\<CodeBase >** элемента требуется **href** атрибута. Нельзя указать диапазон версий в  **\<codeBase >** элемент.  
  
> [!NOTE]
>  Если вы указали подсказка базы кода для сборки, не является строгим именем, должна указывать на базовой папки приложения или ее подкаталог базового каталога приложения.  
  
## <a name="using-the-probing-element"></a>С помощью \<probing > элемент  
 Среда выполнения находит сборки, у которых нет базы кода при проверке. Дополнительные сведения о проверке см. в разделе [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Можно использовать [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) элемент в файле конфигурации приложения для указания подкаталогов, среда выполнения должна использовать при определении расположения сборки. В следующем примере показано, как можно указать каталоги, которые среда выполнения должна выполнять поиск.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **PrivatePath** атрибут содержит каталоги, которые среда выполнения должна искать сборки. Если приложение находится в каталоге C:\Program Files\MyApp, среда выполнения ищет сборки, которые не указаны базы кода в C:\Program Files\MyApp\Bin C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3. Каталоги, указанные в **privatePath** должны быть подкаталогами базового каталога приложения.  
  
## <a name="see-also"></a>См. также

- [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Настройка приложений с помощью файлов конфигурации](index.md)
