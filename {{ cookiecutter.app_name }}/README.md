# Pacotes NuGet

NuGet é o gerenciador de pacotes do .NET, mas vamos obter
apenas os pacotes do seu repositório. Como já sabemos um
pouco como o arquivo de projeto funciona, podemos agora usar
pacotes de terceiros disponíveis no NuGet.

Eu vou utilizar o pacote System.Data.SQLite.Core, mas ele não
é necessário pra utilizar o SQLite no Mono, porque o Mono
disponibiliza a biblioteca Mono.Data.Sqlite. Lembrando que
esse modo de importação pode ser usado em qualquer pacote
disponível no NuGet.

Vamos obter a referencia do pacote no NuGet.

Acesse o [site](https://www.nuget.org/)
Pesquise o nome do pacote: System.Data.SQLite
Na pagina do pacote Sececione **PackageReference**,

```{xml}
<PackageReference Include="System.Data.SQLite.Core" Version="1.0.118" />
```

```{xml}
<?xml version="1.0"?>
<Project>

    <!-- Referências para os pacotes standard -->
    <ItemGroup>
        <Reference Include="System" />
        <Reference Include="System.Data" />
    </ItemGroup>

    <!-- Pacotes do NuGet -->
    <ItemGroup>
        <PackageReference Include="System.Data.SQLite.Core" Version="1.0.118" />
    </ItemGroup>

    <!-- Arquivos do projeto -->
    <ItemGroup>
        <Compile Include="database/sqlite.cs" />
        <Compile Include="app.cs" />
    </ItemGroup>

    <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />

</Project>
```

É bastante intuitiva o arquivo de projeto. Para obter
localmente a biblioteca do NuGet, use o comando
`msbuild -restore`.

A Microsoft possui uma documentação muito boa e podemos
aprender muito com ela. Se você usa uma IDE, ela faz tudo
isso e muito mais configurações no seu projeto, mas como o
objetivo é aprendizagem, então vale apena usar os programas
que estão automatizados por baixo dos panos da IDE.

```{bash}
 msbuild -restore.
```
