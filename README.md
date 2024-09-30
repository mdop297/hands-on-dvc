# hands-on Data versioning with DVC

- create folder images and images_to_use
- >`git init`
- connect with git repo
- >`dvc init`
- >`dvc config core.analytics false`
- >`dvc add images`
- >`git add .gitignore images.dvc`
- >`git commit -m "added raw data"`

- follow this [link](https://dvc.org/doc/user-guide/data-management/remote-storage/google-drive#url-format) to get your google drive ID
    >`dvc remote add -d gdrive gdrive://14CP1hIr2nX_QEs-UXGnDz51RxJa7B5oE` 
- >`pip install dvc[gdrive]`
- follow this [link](https://dvc.org/doc/user-guide/data-management/remote-storage/google-drive#using-a-custom-google-cloud-project-recommended) to get `gdrive_client_id`  and `gdrive_client_secret`.
- > `dvc remote modify gdrive gdrive_client_id 'client-id'` 

- > `dvc remote modify gdrive gdrive_client_secret 'client-secret'`
- Add test user in `OAuth consent screen`
- >`dvc push`
- >`rm -rf .dvc/cache`
- Because DVC has tracked files on google drive, so: `rm -rf ./images` 
- Then, if you need data: 
    >`dvc pull`

*Some changes happened in data source (images folder)*
- >`dvc status`
- >`dvc add ./images`
- >`git add image.dvc`
- >`git commit -m "updated dataset"`
- >`dvc push`