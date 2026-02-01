# Create Packages

  839  mv mywebapp applicationwebapp
  840  git push origin main
  841  git add .; git commit -m "Push to main"
  842  git push origin main
  843  git checkout -b helm-releases
  844  helm lint applicationwebapp/
  845  mkdir packages
  846  helm package applicationwebapp -d packages/
  847  helm repo index packages   --url https://shehbab-kakkar.github.io/applicationwebapp/packages
  848  git checkout helm-releases
  849   git add .; git commit -m "Package release 0.1.1"
  850  git checkout helm-releases
  851  git branch -a
  852  history
  853  git status
  855  git push --set-upstream origin helm-releases

# Add More revisions of chart

helm package applicationwebapp -d packages/
helm repo index packages --merge packages/index.yaml

git add .; git commit -m "Package release 0.1.2"
git push origin helm-releases
