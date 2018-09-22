This CustomSAMLSSOSigner will take the defined keystore information and do the SAML SSO sign process.
Applicable version IS 5.1.0

------------------------
Instructions
--------------------------

1.Modify and implement your logic in  the method  "selectKeyStorebyPreference(String issuer)"
present in the CustomSSOSigner java class to retrieve the Key store information by passing the  issuer to
your service which has the ability to mention the key store information to be used against the issuer.

2.Then build the CustomSAMLSSOSigner project using command "mvn clean install".

3.Shutdown the server if already started.

3.Go to the target directory and copy the SampleJWTTokenGenerator-1.0.jar file to the
<IS_HOME>/repository/components/dropins directory.

4.Then open the file identity.xml file resides in the <IS_HOME>/repository/conf/identity folder.

5.Search the line "org.wso2.carbon.identity.sso.saml.builders.signature.DefaultSSOSigner" and
 replace the it with "org.wso2.custom.sso.signer.CustomSSOSigner".

6.Then Restart the Server.