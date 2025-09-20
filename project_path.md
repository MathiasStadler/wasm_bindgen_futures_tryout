# project path
<!-- keep the format -->
## Which Debian package architecture am I using?

dpkg --print-architecture

## Show which platform available
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->

```
<!-- keep the format -->
## Init plain rust project
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
set -uxo \
&& echo "Step 1 => check the env" \
&& rustup update \
&& echo "DEACTIVATE rustup update  --force" \
&& rustup show \
&& rustup check \
&& echo "DEACTIVATE  rustup toolchain list |xargs rustup toolchain uninstall" \
&& echo "Step 2 => create project"  \
&& touch README.md \
&& ln -s README.md README \
&& cargo init "." \ 
&& cargo add rustfmt \
&& rustup component add rustfmt \
&& mkdir examples \
&& cp src/main.rs examples/example.rs \
&& sed -i -e 's/world/example/g' examples/example.rs \
&& echo "COMMENT rustup toolchain uninstall stable" \
&& echo "COMMENT rustup toolchain install stable" \
&& echo "COMMENT rustup toolchain install nightly" \
&& cargo install --list \
&& cargo update \
&& mkdir tests \
&& echo "Step 3 => build and run the project" \
&& echo "Activate sccache for improve compile time, if it is installed and active"  \
&& export RUSTC_WRAPPER=sccache \
&& cargo build \
&& cargo run \
&& cargo run --example example \
&& echo "Exit code $?"
```

<!-- KtF -->

touch README.md \
&& ln -s README.md README \
&& cargo init "." \
&& cargo add rustfmt \
&& rustup component add rustfmt \
&& mkdir examples \
&& cp src/main.rs examples/example.rs \
&& sed -i -e 's/world/example/g' examples/example.rs \
&& rustup  show \
&& rustup  check \
&& rustup toolchain list |xargs rustup toolchain uninstall \
&& rustup toolchain uninstall stable \
&& rustup toolchain install stable \
&& rustup toolchain install nightly
&& rustup update  --force \
&& rustup show \
&& cargo install --list \
&& cargo update \
&& mkdir tests
<!-- keep the format -->
## Activate toolchain
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
#e.g. nightly
rustup override set nightly
# or stable
rustup override set stable
```
<!-- keep the format -->
## Show which toolchain is active
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustup show
# or better
rustup show |sed -n '/active toolchain/,/^$/p'
```
<!-- keep the format -->
## Show already installed rust binary
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo install --list
```
<!-- keep the format -->
## Update all installed rust binary
<!-- keep the format -->
- Update dependencies as recorded in the local lock file
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo update
```
<!-- keep the format -->

## Install xxx rust binary
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo add 
```
<!-- keep the format -->
## Update outdated crates
<!-- keep the format -->
- List and update installed crates
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
#enable sccache if available
export RUSTC_WRAPPER=sccache
cargo list --update
```
<!-- keep the format -->
cargo install --profile release --target x86_64-unknown-linux-gnu --force wasm-tools
<!-- keep the format -->
## Template bash command
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
```
<!-- keep the format -->
find . -name "*.md" -exec grep EOF {} +
<!-- keep the format -->
>[!TIP]
> <!-- keep the format -->
>```bash <!-- markdownlint-disable-line code-block-style -->
>find . -name "*.md" -exec grep EOF {} +
>```
><!-- keep the format -->
<!-- keep the format -->
## Template create file
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
FILE_NAME="./dummy.sh"
cat > $FILE_NAME << 'EOF'
set -e
#dummy text
EOF
# bash exit code
echo $?
```
<!-- keep the format -->
>[!IMPORTANT]
>For more info follow the project path [![alt text][1]](./project_path.md)
<!-- keep the format -->
>[!NOTE]
>Complete list of github markdown emoji markup [![alt text][1]](https://gist.github.com/rxaviers/7360908)
<!-- keep the format -->
## Garbage garage - Should have no place here :sunglasses: :relaxed: :grin:
<!-- keep the format -->
>[!NOTE]
>Symbol to mark web external links [![alt text][1]](./README.md)
<!-- spell-checker: disable  -->
<!-- keep the format -->
>[!NOTE]
> Wrrong word - for test vscode extension cspell [![alt text][1]](https://cspell.org/docs/Configuration/document-settings)
<!-- spell-checker: enable -->
<!-- keep the format -->
## Useful Marker - Correct view on github [![alt text][1]](https://github.com/MathiasStadler/rust_improve_build_time_debian)
<!-- keep the format -->
-[Markdown] An option to highlight a "Note" and "Warning" using blockquote (Beta) [![alt text][1]](https://github.com/orgs/community/discussions/16925)
<!-- -->
>[!NOTE]  
> Highlights information that users should take into account, even when skimming.
<!-- keep the format -->
>[!NOTE] - Follow the instructions from the website
<!-- keep the format -->
>[!TIP]
> Optional information to help a user be more successful.
<!-- keep the format -->
>[!IMPORTANT]  
> Crucial information necessary for users to succeed.
<!-- keep the format -->
>[!WARNING]  
> Critical content demanding immediate user attention due to potential risks.
<!-- keep the format -->
>[!CAUTION]
> Negative potential consequences of an action.
<!-- keep the format -->
>"✅" [![alt text][1]](https://www.symbolcopy.com/check-mark-symbol.html)
<!-- keep the format -->
>"❌" [![alt text][1]](https://www.symbolcopy.com/check-mark-symbol.html)
<!-- keep the format -->
>"☑" [![alt text][1]](https://www.symbolcopy.com/check-mark-symbol.html)
<!-- keep the format -->
>"☐" [![alt text][1]](https://www.symbolcopy.com/check-mark-symbol.html)

<!-- make folder and download the link sign vai curl -->
<!-- mkdir -p img && curl --create-dirs --output-dir img -O  "https://raw.githubusercontent.com/MathiasStadler/link_symbol_svg/refs/heads/main/link_symbol.svg"-->
<!-- Link sign - Don't Found a better way :-( - You know a better method? - **send me a email** -->
[1]: ./img/link_symbol.svg
<!-- keep the format -->
<!-- keep the format -->
For further steps, see Project path [![alt text][1]](project_path.md)
<!-- make folder and download the link sign vai curl -->
<!-- mkdir -p img && curl --create-dirs --output-dir img -O  "https://raw.githubusercontent.com/MathiasStadler/link_symbol_svg/refs/heads/main/link_symbol.svg"-->
<!-- Link sign - Don't Found a better way :-( - You know a better method? - **send me a email** -->
<!-- keep the format -->