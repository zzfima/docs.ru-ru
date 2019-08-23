---
title: Указание расположения сборки
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 43cd1d0edbb607f69f27661aae3372e93564b3b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932334"
---
# <a name="specifying-an-assemblys-location"></a>Указание расположения сборки
Существует два способа указания расположения сборки:  
  
- С помощью элемента [ CodeBase>.\<](./file-schema/runtime/codebase-element.md)  
  
- С помощью элемента > проверки. [ \<](./file-schema/runtime/probing-element.md)  
  
 Можно также использовать [средство настройки .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) , чтобы указать расположения сборок или указать расположения среды CLR для проверки сборок.  
  
## <a name="using-the-codebase-element"></a>Использование элемента \<CodeBase >  
 Элемент  **\<CodeBase >** можно использовать только в конфигурации компьютера или в файлах политики издателя, которые также перенаправляют версию сборки. Когда среда выполнения определяет используемую версию сборки, она применяет параметр базы кода из файла, который определяет версию. Если не указано ни одной базы кода, среда выполнения проверяет наличие сборки обычным способом. Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md).  
  
 В следующем примере показано, как указать расположение сборки.  
  
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
  
 Атрибут **Version** необходим для всех сборок со строгими именами, но должен быть опущен для сборок, не имеющих строгих имен. **\<CodeBase>** элемента требуется **href** атрибута. В элементе CodeBase > нельзя указывать диапазоны версий.  **\<**  
  
> [!NOTE]
> Если вы предоставляете указание базы кода для сборки, не имеющей строгого имени, подсказка должна указывать на базу приложения или подкаталог базового каталога приложения.  
  
## <a name="using-the-probing-element"></a>\<Использование элемента > зондированием  
 Среда выполнения находит сборки, не имеющие базы кода, путем проверки. Дополнительные сведения о проверке см. в разделе [как среда выполнения находит сборки](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Вы можете использовать [ \<](./file-schema/runtime/probing-element.md) элемент проверки > в файле конфигурации приложения, чтобы указать подкаталоги, которые среда выполнения должна искать при поиске сборки. В следующем примере показано, как указать каталоги, которые должна искать среда выполнения.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Атрибут **privatePath** содержит каталоги, в которых среда выполнения должна искать сборки. Если приложение расположено в папке C:\Program Files\MyApp, среда выполнения будет искать сборки, не указывающие базу кода в C:\Program Филес\мяпп\бин, C:\Program Files\MyApp\Bin2\Subbin и C:\Program Files\MyApp\Bin3. Каталоги, указанные в параметре **privatePath** , должны быть подкаталогами базового каталога приложения.  
  
## <a name="see-also"></a>См. также

- [Сборки в среде CLR](../app-domains/assemblies-in-the-common-language-runtime.md)
- [Программирование с использованием сборок](../app-domains/programming-with-assemblies.md)
- [Обнаружение сборок в среде выполнения](../deployment/how-the-runtime-locates-assemblies.md)
- [Настройка приложений с помощью файлов конфигурации](index.md)
