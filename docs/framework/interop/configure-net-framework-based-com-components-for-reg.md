---
title: "How to: Configure .NET Framework-Based COM Components for Registration-Free Activation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "components [.NET Framework], manifest"
  - "application manifests [.NET Framework]"
  - "manifests [.NET Framework]"
  - "registration-free COM interop, configuring .NET-based components"
  - "activation, registration-free"
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Configure .NET Framework-Based COM Components for Registration-Free Activation
Активация без регистрации для компонентов на основе платформы .NET Framework незначительно сложнее аналогичной процедуры для компонентов COM.  При установке требуются два манифеста:  
  
-   COM\-приложениям требуется манифест приложения в стиле Win32, позволяющий определить управляемый компонент;  
  
-   Компоненты на основе платформы .NET Framework должны иметь манифест компонента для предоставления сведений об активации, необходимых во время выполнения.  
  
 В этом разделе описывается процесс связывания манифеста приложения с приложением, процесс связывания манифеста компонента с компонентом, а также процесс встраивания манифеста компонента в сборку.  
  
### Создание манифеста приложения  
  
1.  С помощью XML\-редактора создайте \(или измените\) манифест приложения, принадлежащий COM\-приложению, которое взаимодействует с одним или несколькими управляемыми компонентами.  
  
2.  В начало файла вставьте следующий стандартный заголовок:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     Сведения об элементах манифеста и их атрибутах можно получить с помощью поиска в библиотеке MSDN по ключевым словам "справка о манифестах приложений".  
  
3.  Укажите владельца манифеста.  В следующем примере владельцем файла манифеста является `myComApp` версии 1.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  Укажите зависимые сборки.  В следующем примере `myComApp` зависит от `myManagedComp`.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  Присвойте файлу манифеста имя и сохраните файл.  Имя манифеста приложения — это имя исполняемого файла сборки с расширением MANIFEST.  Например, имя файла манифеста приложения для myComApp.exe — myComApp.exe.manifest.  
  
 Манифест приложения можно установить в ту же папку, что и COM\-приложение.  Либо Его можно добавить в виде ресурса в исполняемый файл \(EXE\) приложения.  Дополнительные сведения можно получить с помощью поиска в библиотеке MSDN по ключевым словам "Параллельные сборки".  
  
#### Создание манифеста компонента  
  
1.  С помощью XML\-редактора создайте манифест компонента, который будет описывать управляемую сборку.  
  
2.  В начало файла вставьте следующий стандартный заголовок:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  Укажите владельца файла.  Элемент `<assemblyIdentity>` элемента `<dependentAssembly>` в файле манифеста приложения должен соответствовать аналогичному элементу манифеста компонента.  В следующем примере владельцем файла манифеста является `myManagedComp` версии 1.2.3.4.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  Укажите каждый класс сборки.  С помощью элемента `<clrClass>` уникальным образом определите каждый класс в управляемой сборке.  Элемент, являющийся дочерним для элемента `<assembly>`, имеет атрибуты, приведенные в следующей таблице.  
  
    |Атрибут|Описание|Требуется|  
    |-------------|--------------|---------------|  
    |`clsid`|Идентификатор, который задает активируемый класс.|Да|  
    |`description`|Строка, предоставляющая пользователю сведения о компоненте.  Значение по умолчанию — пустая строка.|Нет|  
    |`name`|Строка, представляющая управляемый класс.|Да|  
    |`progid`|Идентификатор, используемый для отложенной активации.|Нет|  
    |`threadingModel`|Модель потоков COM. «Both» значение по умолчанию.|Нет|  
    |`runtimeVersion`|Задает используемую версию среды CLR.  Если не задать данный атрибут, а среда CLR еще не загружена, компонент загружается в последнюю версию установленной среды CLR, которая предшествует среде CLR версии 4.  Если задать значения v1.0.3705, v1.1.4322 или v2.0.50727, версия автоматически накатывается до последней версии среды CLR, которая предшествует среде CLR версии 4 \(обычно v2.0.50727\).  Если загружена другая версия среды CLR, а заданная версия может быть загружена параллельно внутрипроцессно, загружается заданная версия; в противном случае используется загруженная среда CLR.  Это может вызвать сбой загрузки.|Нет|  
    |`tlbid`|Идентификатор библиотеки типов, содержащий сведения о типе для класса.|Нет|  
  
     Все теги атрибутов зависят от регистра.  Значения CLSID, ProgID, модели потоков и номер версии среды выполнения можно получить, найдя в библиотеке экспортированных типов сборку с помощью программы просмотра объектов OLE\/COM \(Oleview.exe\).  
  
     Следующий манифест компонента идентифицирует два класса: `testClass1` и `testClass2`.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  Присвойте файлу манифеста имя и сохраните файл.  Имя манифеста компонента — это имя библиотеки сборки с расширением MANIFEST.  Например, файл манифеста библиотеки myManagedComp.dll будет иметь имя myManagedComp.manifest.  
  
 Манифест компонента необходимо встроить в сборку в качестве ресурса.  
  
#### Встраивание манифеста компонента в управляемую сборку  
  
1.  Создайте описание ресурса, содержащее следующую инструкцию:  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     В этой инструкции `myManagedComp.manifest` — это имя встраиваемого манифеста компонента.  Для этого примера именем файла скрипта является `myresource.rc`.  
  
2.  Выполните компиляцию скрипта с помощью компилятора ресурсов Microsoft Windows \(Rc.exe\).  В командной строке введите следующую команду:  
  
     `rc myresource.rc`  
  
     Программа Rc.exe создает файл ресурсов `myresource.res`.  
  
3.  Снова выполните компиляцию исходного файла сборки и укажите файл ресурсов с помощью параметра **\/win32res**:  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     В этом случае `myresource.res` — имя файла ресурсов, содержащего встроенный ресурс.  
  
## См. также  
 [Registration\-Free COM Interop](../../../docs/framework/interop/registration-free-com-interop.md)   
 [Requirements for Registration\-Free COM Interop](http://msdn.microsoft.com/ru-ru/0c43bc57-eecf-4e6c-8114-490141cce4da)   
 [Configuring COM Components for Registration\-Free Activation](http://msdn.microsoft.com/ru-ru/bfe9b02f-d964-4784-960e-a1f94692fbfe)   
 [Свободная от Регистрация активация компонентов на базе .NET. Пошаговое руководство](http://go.microsoft.com/fwlink/?LinkId=158812)