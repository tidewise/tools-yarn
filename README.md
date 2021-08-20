A fake package to allow us to install Yarn for an Autoproj workspace

Just point Autoproj to this reposity for the following package

~~~
import_package "tools/yarn" do |pkg|
    pkg.env_add_path File.join(pkg.srcdir, "node_modules", ".bin")
    pkg.post_install do
        pkg.run "npm", "install", "yarn"
    end
end
~~~

