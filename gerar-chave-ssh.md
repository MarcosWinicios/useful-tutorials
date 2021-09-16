    **Gerando a chave na máquina local**

    1. Gerar a chave pelo terminal

  ```bash
     ssh-keygen -t ed25519 -C user@gmail.com
  ```

        - lembrar de colocar o C maiúsculo
        -  ed25519: Tipo de criptografia da chave.(Outro tipo seria o rsa)

    2. Local onde a chave será salva

        - Recomendado não alterar

    3. Senha(opcinal)

    4. Mostra local onde a chave foi salva
        - Duas chaves são criadas: Privada e Publica(nome da chave com .pub na frente) 

    5. Acessar o diretorio em que as chaves foram criadas

 
```bash
  - cd /pasta/pasta/.ssh 
```

        linux: home/usuario/.ssh
        windows: /c/Users/usuario/.ssh

        - ls: Listar os arquivso dentro da pasta

    **Vinculando a chave gerada com o github**
    
    6. Copiar o conteúdo da chave pública

```bash 
    cat nomedachave(geralmente é id_ed25519.pub)
```    
           - Copiar o conteúdo da chave

    7. Colar no SSH and GPG keys no GitHub
           - Iserir um título para identificar de onde vem a chave
           - Colar a chave
           - Adicionar
    
    *Validar a conexão novamente na máquina local*

    8. Inicializar o ssh-keygen(Entidade responsável por lidar com as chaves ssh)
    

```bash 
  eval $(ssh-agent -s)
```
        - o s tem que ser minúsculo
        
        - Saída: Agent pid <numero>

    9. Entregar a chave para o Agent gerado

  ```bash 
          ssh-add <caminho da chave privada(Se estiver dentro da pasta da chave, basta digitar o nome da mesma)>
  ``` 
        - Significado: Sempre que chegar uma solicitação com chave pública, ele vai utilizar esta chave privada para discriptografar
    
    10. Inserir senha salva para esta chave

        
