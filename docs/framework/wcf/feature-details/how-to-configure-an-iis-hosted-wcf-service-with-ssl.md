---
title: Практическое руководство. Как настраивать протокол SSL в службе WCF, размещенной в IIS
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8d3bbb1ceab8a3bc7e5e209fda29fd574110b4f7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326454"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Практическое руководство. Как настраивать протокол SSL в службе WCF, размещенной в IIS
В этом разделе описано, как настроить размещенную в IIS службу WCF для использования безопасности транспорта HTTP. Для безопасности транспорта HTTP требуется, чтобы SSL-сертификат был зарегистрирован в службах IIS. Если SSL-сертификат не установлен, для создания тестового сертификата можно использовать службы IIS. Затем необходимо добавить SSL-привязку для проекта веб-сайта и установить свойства проверки подлинности веб-сайта. Наконец, необходимо настроить службу WCF на использование протокола HTTPS.  
  
### <a name="creating-a-self-signed-certificate"></a>Создание самозаверяющего сертификата  
  
1. Откройте диспетчер служб IIS (inetmgr.exe) и выберите имя компьютера в левой части представления в виде дерева. В правой части экрана выберите сертификаты сервера  
  
     ![Главный экран диспетчера IIS](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. В окне сертификатов сервера щелкните **создать самозаверяющий сертификат...** Связь.  
  
     ![Создание самозаверяющего&#45;сертификата со службами IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. Введите понятное имя для самозаверяющего сертификата и нажмите кнопку **ОК**.  
  
     ![Создание собственные&#45;диалоговое окно сертификата подписи](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")  
  
     Сведения о только что созданный самозаверяющий сертификат теперь отображаются в **сертификаты сервера** окна.  
  
     ![Окно "сертификат сервера"](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     Созданный сертификат устанавливается в хранилище доверенных корневых центров сертификации.  
  
### <a name="add-ssl-binding"></a>Добавление привязки SSL  
  
1. По-прежнему в диспетчер служб IIS, разверните **сайты** папку и затем **Default Web Site** папку в представлении в виде дерева в левой части экрана.  
  
2. Нажмите кнопку **привязки...** Ссылка в **действия** в правой верхней части окна.  
  
     ![Добавление привязки SSL](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. В окне «привязки сайта» щелкните **добавить** кнопки.  
  
     ![Диалоговое окно привязки сайта](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. В **Добавление привязки сайта** диалоговом окне выберите https в качестве типа и понятное имя самозаверяющего сертификата, который вы только что создан.  
  
     ![Пример привязки сайта](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Настройка виртуального каталога для SSL  
  
1. В диспетчере служб IIS выберите виртуальный каталог, содержащий безопасную службу WCF.  
  
2. В центральной области окна, выберите **параметры SSL** в разделе IIS.  
  
     ![Параметры SSL для виртуального каталога](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. На панели параметров SSL выберите **Требовать SSL** флажок и нажмите кнопку **применить** ссылку в **действия** разделе правой стороны экрана.  
  
     ![Параметры SSL виртуального каталога](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Настройка службы WCF для безопасности транспорта HTTP  
  
1. В файле web.config службы WCF настройте привязку HTTP на использование безопасности транспорта, как показано в следующем фрагменте XML.  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. Укажите службу и конечную точку службы, как показано в следующем фрагменте XML.  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример файла web.config для службы WCF, использующей безопасность транспорта HTTP  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Размещение в службах IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [Инструкции по размещению в службах IIS](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [Рекомендации по размещению в службах IIS](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Размещение в службах IIS с использованием встроенного кода](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
