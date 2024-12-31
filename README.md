# symmetric-encrypt-decrypt-action

Performs symmetric encryption or decryption on the provided data.

<!-- actdocs start -->

## Description

This action performs symmetric encryption and decryption using AES-256-CBC,
supporting both operations with a provided key and IV.
It can be integrated into workflows to securely encrypt or decrypt data.
The key and IV are hashed using SHA-256 to ensure secure operations,
and the action performs encryption or decryption based on the specified operation.

## Usage

### Encrypt

```yaml
  steps:
    - name: Symmetric Encrypt Decrypt
      uses: tmknom/symmetric-encrypt-decrypt-action@v0
      with:
        data: plaintext
        operation: encrypt
```

### Decrypt

```yaml
  steps:
    - name: Symmetric Encrypt Decrypt
      uses: tmknom/symmetric-encrypt-decrypt-action@v0
      with:
        data: ciphertext
        operation: decrypt
```

## Inputs

| Name | Description | Default | Required |
| :--- | :---------- | :------ | :------: |
| data | The data to be encrypted or decrypted. Provide as plaintext for encryption, or ciphertext for decryption. | n/a | yes |
| iv | The initialization vector used for encryption. | `${{ github.sha }}-${{ github.run_id }}-${{ github.run_attempt }}-${{ github.actor_id }}` | yes |
| key | The encryption key used for both encryption and decryption. | `${{ github.sha }}-${{ github.run_id }}-${{ github.run_attempt }}-${{ github.workflow_sha }}` | yes |
| operation | The operation to perform, which can be either encrypt or decrypt. | n/a | yes |

## Outputs

| Name | Description |
| :--- | :---------- |
| result | The result of encryption or decryption (ciphertext or plaintext). |

<!-- actdocs end -->

## Permissions

N/A

## FAQ

N/A

## Related projects

N/A

## Release notes

See [GitHub Releases][releases].

[releases]: https://github.com/tmknom/symmetric-encrypt-decrypt-action/releases
