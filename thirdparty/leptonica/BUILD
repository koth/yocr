package(default_visibility = ["//visibility:public"])

package_name = "leptonica"
package_version = "1.73"

package_file = package_name + "-" + package_version + ".tar.gz"
package_dir = package_name + "-" + package_version

genrule(
    name = "leptonica-srcs",
    srcs = [
        package_file, 
    ],
    outs = 
    [
        "allheaders.h",
        "alltypes.h",
        'environ.h',
  'array.h',
  'bbuffer.h',
  'heap.h',
  'list.h',
  'ptra.h',
  'queue.h',
  'rbtree.h',
  'stack.h',
  'arrayaccess.h',
  'bmf.h',
  'ccbord.h',
  'dewarp.h',
  'gplot.h',
  'imageio.h',
  'jbclass.h',
  'morph.h',
  'pix.h',
  'recog.h',
  'regutils.h',
  'stringcode.h',
  'sudoku.h',
  'watershed.h',
   "liblept173.a", 
    ],
    cmd = "\n".join([
        "export INSTALL_DIR=$$(pwd)/$(@D)",
        "echo dir is: $$INSTALL_DIR",
        "export TMP_DIR=$$(mktemp -d -t leptonica.XXXXX)",
        "mkdir -p $$TMP_DIR",
        "cp -R $(SRCS) $$TMP_DIR",
        "cd $$TMP_DIR",
        "tar xfz " + package_file,
        "cd " + package_dir,
        "mkdir build",
        "cd build",
        "cmake .. -DSTATIC=1",
        "make",
        "cp ../src/*.h $$INSTALL_DIR",
        "cp src/liblept173.a $$INSTALL_DIR",
        "rm -rf $$TMP_DIR",
    ]),
)

cc_library(
    name = "leptonica",
    srcs = [
        "empty.cc",
        "liblept173.a",
        "allheaders.h",
        "alltypes.h",
        'environ.h',
  'array.h',
  'bbuffer.h',
  'heap.h',
  'list.h',
  'ptra.h',
  'queue.h',
  'rbtree.h',
  'stack.h',
  'arrayaccess.h',
  'bmf.h',
  'ccbord.h',
  'dewarp.h',
  'gplot.h',
  'imageio.h',
  'jbclass.h',
  'morph.h',
  'pix.h',
  'recog.h',
  'regutils.h',
  'stringcode.h',
  'sudoku.h',
  'watershed.h',
    ],
linkstatic=1,
)
