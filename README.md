# prevent_norm_error-script

Thw script advice you with a red text on the screen how much norm errors are in your directory when you push

place at the top of your .zshrc or .bashrc this function:

git() {
  if [[ "$1" == "push" ]]; then
    ~/scripts/pre-push/prevent_norm_error.sh "${@:2}"
  else
    command git "$@"
  fi
}
