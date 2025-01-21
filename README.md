# prevent_norm_error-script
place at the top of your .zshrc or .bashrc this function:

git() {
  if [[ "$1" == "push" ]]; then
    ~/scripts/pre-push/prevent_norm_error.sh "${@:2}"
  else
    command git "$@"
  fi
}
