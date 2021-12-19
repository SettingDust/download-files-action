# download-file-action

![Workflow To Test Action](https://github.com/carlosperate/download-file-action/workflows/Workflow%20To%20Test%20Action/badge.svg)

GitHub Action to download a file from the internet into the workspace.


## Inputs

- `file-url`: (**Required**) The URL of the file to download.
- `file-name`: (**Optional**) A new filename to rename the downloaded file.
- `location`: (**Optional**) A path to download the file.
- `md5`: (**Optional**) An MD5 hash to verify the download.


## Outputs

- `file-path`: The full path to the downloaded file.


## Example usage

```yml
- name: Download a file
    uses: carlosperate/download-file-action@v1.0.3
    id: download-file
    with:
        file-url: 'https://github.com/carlosperate/download-file-action/archive/refs/tags/v1.0.3.tar.gz'
        file-name: 'new_filename.tar.gz'
        location: './new-folder-to-be-created'
        md5: 'e3b51204dedc75588ca164a26b51610d'
- name: Print the file path
    run: echo "The file was downloaded to ${{ steps.download-file.outputs.file-path }}"
```
