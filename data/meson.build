i18n.merge_file(
    input: meson.project_name() + '.desktop.in',
    output: meson.project_name() + '.desktop',
    po_dir: join_paths(meson.source_root (), 'po', 'extra'),
    type: 'desktop',
    install_dir: join_paths(get_option('sysconfdir'), 'xdg', 'autostart'),
    install: true
)

install_data(
    'io.elementary.onboarding.gschema.xml',
    install_dir: join_paths(get_option('datadir'), 'glib-2.0', 'schemas')
)

# Test the desktop file
validate_desktop_exe = find_program('desktop-file-validate')
test ('Validate desktop file', validate_desktop_exe,
    args: join_paths(meson.current_build_dir (), meson.project_name() + '.desktop')
)
