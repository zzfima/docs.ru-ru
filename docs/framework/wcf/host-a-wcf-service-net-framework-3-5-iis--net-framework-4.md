---
title: "Как разместить службу WCF, написанную для.NET Framework 3.5 в IIS, которая работает в среде в .NET Framework 4 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Как разместить службу WCF, написанную для.NET Framework 3.5 в IIS, которая работает в среде в .NET Framework 4
При размещении службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], написанной для платформы [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] на компьютере, на котором установлена платформа [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], может возникнуть исключение <xref:System.ServiceModel.ProtocolException> со следующим текстом.  
  
```Output  
Необработанное исключение: System.ServiceModel.ProtocolException: Тип содержимого ответного сообщения, text/html; charset=utf-8, не соответствует типу содержимого привязки (application/soap+xml; charset=utf-8).При использовании пользовательского кодировщика убедитесь, что метод IsContentTypeSupported реализован надлежащим образом.Первые 1024 байта ответа: <html>    <заголовок>        <название>Домен или пул приложения в настоящий момент использует .NET Framework версии 4 или более поздней.Это может произойти, если параметры служб IIS были заданы на 4.0 или более позднюю версию для этого веб-приложения либо если используется ASP.NET Web Development Server версии 4.0 или более поздней.Элемент <compilation> в файле Web.config для этого веб-приложения не содержит требуемый атрибут «targetFrameworkMoniker» для этой версии .NET Framework (например, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">').Дополните файл Web.config этим атрибутом или настройте веб-приложение на использование другой версии .NET Framework.</название>...  
```  
  
 При попытке перехода к SVC\-файлу службы может отобразиться страница ошибки со следующим текстом.  
  
```Output  
Домен или пул приложения в настоящий момент использует .NET Framework 4.0 или более позднюю версию.Это может произойти, если параметры служб IIS были заданы на 4.0 или более позднюю версию для этого веб-приложения либо если используется ASP.NET Web Development Server версии 4.0 или более поздней.Элемент <compilation> в файле Web.config для этого веб-приложения не содержит требуемый атрибут «targetFrameworkMoniker» для этой версии .NET Framework (например, «<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">»).Дополните файл Web.config этим атрибутом или настройте в веб-приложении использование другой версии .NET Framework.  
```  
  
 Эти ошибки возникают из\-за работы домена приложения служб IIS под управлением платформы [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], в то время как службе WCF требуется платформа [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].В этом разделе описываются изменения, которые необходимо выполнить для запуска службы.  
  
 Затем следует найти элемент \<`compilers`\> и изменить параметр поставщика CompilerVersion, задав для него значение 4.0.По умолчанию в элементе \<`compilers`\> есть два элемента \<`compiler`\>.Необходимо обновить параметр поставщика CompilerVersion для обоих элементов, как показано в следующем примере.  
  
```  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### Добавьте необходимый атрибут targetFramework  
  
1.  Откройте файл службы Web.config и найдите элемент \<`compilation`\>.  
  
2.  Добавьте атрибут `targetFramework` к элементу \<`compilation`\>, как показано в следующем примере.  
  
    ```  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3.  Найдите элемент \<`compilers`\> и измените параметр поставщика CompilerVersion, задав для него значение 4.0.По умолчанию в элементе \<`compilers`\> есть два элемента \<`compiler`\>.Необходимо обновить параметр поставщика CompilerVersion для обоих элементов, как показано в следующем примере.  
  
    ```  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```